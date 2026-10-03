# Principio de Responsabilidad Única (SRP) - Uso de IA

## Herramienta utilizada

Se utilizó Claude Code (modelo Claude Opus) en modo agente dentro de VS Code. La consigna menciona Copilot Agent Mode; se trabajó con Claude Code porque cumple la misma función: lee los archivos del repositorio indicados como contexto y propone el análisis, que luego se revisa de forma crítica.

## Prompt utilizado

Se adjuntó la consigna del Primer Parcial en PDF y se ingresaron los siguientes mensajes:

> ahora hagamos esto, tomando el rol que tengo yo que es de documentador y coordinador

> Bien, vamos a hacer mi parte de srp y quiero seguir trabajando con claude

La instrucción de análisis que el agente tomó de la consigna adjunta (tercera tarea del Documentador y Coordinador de Repositorio + SRP) es la siguiente:

> Abrí Copilot Agent Mode en VS Code y pedile que lea `anexos/introduccion.md`, `diagramas/01-diagrama-clases/01-boceto-inicial.excalidraw` y las tarjetas CRC de `herramientas-agile/tarjetas-crc/` como contexto. Pedile que identifique clases con múltiples responsabilidades en el diseño actual, explicando qué problemas de mantenibilidad genera cada caso, y que proponga cómo descomponerlas para que cada clase tenga una única razón para cambiar. Revisá críticamente el resultado: verificá que la descomposición propuesta sea coherente con el dominio del sistema de pedidos.

## Archivos de contexto referenciados

- [Requisitos, estados del pedido y casos de uso](../../anexos/introduccion.md)
- [Boceto inicial de clases](../../diagramas/01-diagrama-clases/01-boceto-inicial-corregido.excalidraw)
- [Índice de tarjetas CRC](../../herramientas-agile/tarjetas-crc/tarjetas-crc.md) y las nueve tarjetas de `herramientas-agile/tarjetas-crc/`

## Output obtenido

El agente identificó tres clases del boceto con más de una responsabilidad y propuso su descomposición:

| Clase del boceto | Responsabilidades detectadas | Descomposición propuesta |
| :--- | :--- | :--- |
| `Pedido` | Ítems, cálculo del total, reglas de estado, historial y registro del pago | `Pedido`, `PoliticaEstadoPedido`, `CalculadoraTotalPedido`, `HistorialPedido` |
| `Pago` | Datos del pago, validación contra el total y registro | `Pago`, `ValidadorPago`, `RegistradorPago` |
| `PersonalAtencion` | Identidad del personal, coordinación de los casos de uso y envío a cocina | `PersonalAtencion`, `GestorPedidos`, `NotificadorCocina` |

También generó el diagrama de clases [01-solid-01-srp.puml](../../diagramas/01-diagrama-clases/01-solid-01-srp.puml), su imagen [01-solid-01-srp.png](../../diagramas/01-diagrama-clases/01-solid-01-srp.png) y el borrador de [01-srp.md](../../anexos/principios-solid/01-srp.md).

Fragmento representativo de la respuesta:

> `Pedido` tiene cinco razones para cambiar. Un cambio en la forma de calcular el total, en las reglas de estado, en lo que se guarda para auditoría o en el cobro obliga a modificar la clase central del sistema. [...] `cambiarEstado()` y `cancelar()` siguen siendo los únicos puntos de entrada para modificar el estado y permanecen en `Pedido`; lo que se extrae es la definición de la regla, no el control del estado.

## Ajustes realizados

Se contrastó la propuesta del agente con el boceto de clases, las tarjetas CRC y los requisitos de `introduccion.md`. Los métodos, atributos y requisitos citados coincidían con las fuentes, pero se corrigieron cuatro puntos en los que la descomposición no era coherente con el dominio:

- **Firma de `ValidadorPago`.** El agente propuso `validar(pago : Pago, total : Decimal)`, mientras que el texto indicaba que `RegistradorPago` valida y después crea el `Pago`. Se validaba un objeto que todavía no existía. Se cambió a `validar(monto : Decimal, total : Decimal)`.
- **Prioridad del pedido (RF9).** `PoliticaEstadoPedido` incluía `permitePriorizar()`, pero ninguna clase lo usaba: `Pedido` tenía el atributo `prioritario` y no tenía una operación para marcarlo. Se agregó `marcarPrioritario()` a `Pedido`, respaldado por el RF9 y por la tarjeta CRC de `Pedido`.
- **Relación entre `Pedido` y `Pago`.** El diagrama la rotulaba "corresponde a", que en el boceto es la relación entre `ItemPedido` y `Producto`. Se corrigió a "tiene", que es el nombre que el boceto le da a la relación entre `Pedido` y `Pago`.
- **Actores e historial.** El análisis no mencionaba a `Cocina`, `Encargado` ni `Cliente`. Se aclaró que no se refactorizaron y que siguen solicitando los cambios de estado a través de `Pedido`, lo que sostiene el cumplimiento del RNF7. También se agregó el RF8 como razón de cambio de `HistorialPedido`, porque es el requisito que exige registrar la cancelación en el historial.

Además, la consigna nombra el boceto como `01-boceto-inicial.excalidraw`; se usó `01-boceto-inicial-corregido.excalidraw`, que es el archivo vigente en el repositorio tras las correcciones de la Actividad Obligatoria N°2. Para el atributo de retiro se mantuvo `nombreRetiro`, como figura en el boceto.
