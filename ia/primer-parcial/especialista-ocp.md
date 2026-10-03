# Especialista en Principios de Extensión - OCP

## Herramienta utilizada
Se utilizó Copilot en modo agente dentro de VS Code
## Prompt utilizado
ACTUA COMO UN ESPECIALISTA EN DISEÑO ORIENTADO A OBJETOS Y ARQUITECTURA DE SOFTWARE, EN PRINCIPIO SOLID. LEE LAS consignas.md DE MODO GENERAL PARA TENER UNA IDEA Y DESDE AHÍ CUMPLE LAS SIGUIENTES INSTRUCCIONES: 
1)	EN EL ARCHIVO anexos/principios-solid/02ocp.md COPIA EL ARCHIVO plantilla.md
2)	EVALUANDO LA INFORMACION DE anexos.md, diagramas/01-diagrama-clases/01-boceto-inicial-excalidraw y las tarjetas CRC de herramientas-agile/tarjetas-crc como contexto.
3)	IDENTIFICA CLASES CON LOGICA QUE PODRIAN REEMPLAZARSE CON HERENCIA O POLIMORFISMO, PROPONIENDO EXTENSIONES SIN MODIFICAR CODIGO EXISTENTE.
4)	POSTERIORMENTE DENTRO DE anexos/principios-solid/02-ocp.md COMPLETA LA PLANILLA QUE COPIASTE, RESPETANDO LOS TITULOS Y SUBTITULOS y completando y sustituyendo el desarrollo de cada uno de estos.
5)	EL DIAGRAMA QUE DEBES CREAR DEBE LLEVAR COMO NOMBRE 01-solid-02-ocp.puml y su versión exportada  01-solid-02-ocp.pgn, ESTE DIAGRAMA DEBE MOSTRAR TANTO EXTENSIBILIDAD COMO JERARQUIAS CORRECTAS Y DEBE ESTAR DENTRO DE LA CARPETA diagramas/01-diagrama-clases/

Se consultó la consigna general de la materia y se trabajó con los siguientes artefactos de contexto:

- [anexos/introduccion.md](../../anexos/introduccion.md)
- [diagramas/01-diagrama-clases/01-boceto-inicial-corregido.excalidraw](../../diagramas/01-diagrama-clases/01-boceto-inicial-corregido.excalidraw)
- [herramientas-agile/tarjetas-crc/tarjetas-crc.md](../../herramientas-agile/tarjetas-crc/tarjetas-crc.md)

## Prompt utilizado resumido:

> Analiza el sistema de pedidos del kiosco y aplica el Principio Abierto/Cerrado. Identifica clases con lógica condicional que puedan modelarse mediante jerarquías o polimorfismo, proponiendo extensiones sin modificar el código existente. Considera el ciclo de vida del pedido, las formas de pago y la notificación a cocina. Luego, documenta la propuesta con una explicación técnica y un diagrama UML que muestre extensibilidad correcta y jerarquía apropiada.

## Archivos de contexto referenciados

- Documento OCP: [anexos/principios-solid/02-ocp.md](../../anexos/principios-solid/02-ocp.md)
- Diagrama UML: [diagramas/01-diagrama-clases/01-solid-02-ocp.puml](../../diagramas/01-diagrama-clases/01-solid-02-ocp.puml)
- Exportación visual: [diagramas/01-diagrama-clases/01-solid-02-ocp.png](../../diagramas/01-diagrama-clases/01-solid-02-ocp.png)

## Output obtenido

El agente identificó tres puntos de variación del dominio que pueden resolverse con herencia y polimorfismo sin tocar la lógica ya validada:

| Punto de variación | Problema del diseño inicial | Propuesta OCP |
| :--- | :--- | :--- |
| `EstadoPedido` | El pedido tiene reglas distintas según su estado: modificar, cancelar, priorizar o entregar. Si esas decisiones están embebidas en condicionales, cada nuevo estado exige tocar la misma lógica central. | Crear una jerarquía `EstadoPedido` con subclases `Recibido`, `EnPreparacion`, `Listo`, `Entregado` y `Cancelado`, cada una con su propia respuesta a la operación común. |
| `MetodoPago` | El registro del cobro puede cambiar con efectivo, tarjeta, QR o puntos, y la lógica de pago queda acoplada a la coordinación principal. | Definir la abstracción `MetodoPago` y especializarla en estrategias concretas, sin cambiar la coordinación de `RegistradorPago`. |
| `CanalNotificacion` | El RF5 exige notificar a cocina y puede variar el medio de comunicación (interno, WhatsApp, display, etc.). | Crear `CanalNotificacion` y dejar que `GestorPedidos` elija el canal al registrar el pedido, sin modificar la lógica principal. |

También generó el diagrama de clases [01-solid-02-ocp.puml](../../diagramas/01-diagrama-clases/01-solid-02-ocp.puml), su imagen [01-solid-02-ocp.png](../../diagramas/01-diagrama-clases/01-solid-02-ocp.png) y el borrador de [02-ocp.md](../../anexos/principios-solid/02-ocp.md).

Fragmento representativo de la respuesta:

> `Pedido` depende de abstracciones de estado y pago (`EstadoPedido`, `MetodoPago`), mientras que la notificación a cocina queda coordinada por `GestorPedidos` a través de `CanalNotificacion`. Esto coincide con el diagrama: `Pedido` no usa `CanalNotificacion` directamente, y el envío se realiza desde el gestor al registrar el pedido.

> `RegistradorPago` ya no necesita conocer todos los casos concretos de cobro. Depende de `MetodoPago` y cada estrategia concreta implementa una forma de registro distinta. Esto permite ampliar con `PagoTransferencia` o `PagoCuentaCorriente` sin tocar la clase que coordina la operación.

## Ajustes realizados al resultado

Se contrastó la propuesta del agente con el boceto de clases, las tarjetas CRC, el diagrama OCP y el RF5. Los puntos corregidos fueron los siguientes:

- **Responsabilidad de la notificación a cocina.** La propuesta original podía sugerir que `Pedido` o `CanalNotificacion` eran quienes emitían el aviso. Se dejó explícito que la coordinación la realiza `GestorPedidos`, y que la relación con `CocinaInterna` ocurre al registrar el pedido.
- **Duplicación del registro de pago.** El diagrama no podía volver a introducir `registrarPago()` en `Pedido` porque ese método ya había sido quitado en el SRP como duplicado con `RegistradorPago`. Se mantuvo el diseño consistente con la firma `registrar(pedido : Pedido, metodo : MetodoPago, monto : Decimal) : Pago`.
- **Dependencia de `Pedido` con `RegistradorPago`.** La relación se mantuvo como una dependencia explícita del pedido hacia el registrador, sin cambiar la estructura del diagrama, pero explicitando que `RegistradorPago` recibe el `Pedido` como parámetro cuando procesa el cobro.
- **Coherencia con el OCP.** Se reforzó que la variación del negocio queda encapsulada en jerarquías de extensión (`EstadoPedido`, `MetodoPago`, `CanalNotificacion`), mientras el cliente (`Pedido`, `GestorPedidos`, `RegistradorPago`) conserva la lógica estable y reutilizable.
- **Alineación con el dominio.** El análisis se centró en los requisitos del kiosco: ciclo de vida del pedido, tipos de pago y avisos a cocina. No se introdujeron nuevas responsabilidades que no estuvieran sustentadas por el boceto ni por las tarjetas CRC.

Con estos ajustes, la propuesta OCP queda coherente con el diagrama y con la arquitectura ya validada para el resto de los principios SOLID.






