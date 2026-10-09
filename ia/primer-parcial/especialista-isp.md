# Especialista en Segregación de Interfaces (ISP)

## Prompt utilizado

```text
Leé como contexto los siguientes archivos del repositorio:

- anexos/introduccion.md
- diagramas/01-diagrama-clases/01-boceto-inicial.excalidraw
- todas las tarjetas CRC ubicadas en herramientas-agile/tarjetas-crc/

Analizá el diseño actual de SistemaPedidos aplicando el Principio de Segregación de Interfaces (ISP).

Quiero que:

1. Identifiques conjuntos de responsabilidades y métodos ya existentes en las clases del boceto que puedan abstraerse en interfaces cohesivas y especializadas.
2. Detectes qué posible interfaz "gorda" debería evitarse porque obligaría a una clase a depender o implementar métodos que no necesita.
3. Para cada interfaz propuesta indiques:
   - nombre sugerido;
   - métodos existentes que contendría;
   - clase o clases existentes que la implementarían;
   - justificación basada en las responsabilidades actuales del dominio.
4. No inventes nuevas clases, métodos, actores ni requisitos que no estén respaldados por los archivos de contexto.
5. Evitá interfaces genéricas sin significado concreto para el dominio de Sabor Kiosco.
6. Compará especialmente estas dos posibilidades:
   - abstraer las responsabilidades de PersonalAtencion, Cocina y Encargado en interfaces especializadas;
   - segregar las distintas responsabilidades actualmente concentradas en Pedido mediante interfaces específicas.
7. Indicá ventajas, problemas o sobreingeniería que veas en cada alternativa y cuál está mejor respaldada por el diseño actual.

No modifiques archivos. Solo realizá el análisis y devolvé las propuestas para revisión crítica.
```

## Archivos de contexto referenciados

Para realizar el análisis con Copilot Agent Mode se indicó como contexto:

- `anexos/introduccion.md`
- `diagramas/01-diagrama-clases/01-boceto-inicial.excalidraw`
- las tarjetas CRC ubicadas en `herramientas-agile/tarjetas-crc/`

Durante el análisis, Copilot informó que el archivo `01-boceto-inicial.excalidraw` no existía con ese nombre exacto en el repositorio y utilizó en su lugar el boceto vigente `01-boceto-inicial-corregido.excalidraw`.

## Output obtenido

Copilot analizó dos alternativas principales para aplicar ISP al diseño existente.

La primera alternativa consistió en abstraer responsabilidades de `PersonalAtencion`, `Cocina` y `Encargado` mediante interfaces especializadas. Entre las propuestas aparecieron contratos relacionados con la toma y derivación de pedidos, preparación, consulta de pedidos activos y gestión del ciclo de vida.

La segunda alternativa se centró en la clase `Pedido`, identificando distintos grupos de responsabilidades dentro de sus métodos actuales:

- edición del pedido: `agregarItem()`, `quitarItem()` y `modificarItem()`;
- cálculo del total: `calcularTotal()`;
- ciclo de vida: `cambiarEstado()` y `cancelar()`;
- registro del pago: `registrarPago()`.

Copilot señaló que la segregación de `Pedido` estaba mejor respaldada por el diseño actual, ya que el boceto y las tarjetas CRC muestran en esa clase conjuntos de operaciones con finalidades diferentes.

También advirtió que no debía proponerse una única interfaz general, como `GestionPedido`, que reuniera edición, cálculo, ciclo de vida, pago y otras operaciones del sistema, porque podría obligar a los clientes a depender de métodos que no utilizan.

Además, indicó que una segregación excesiva en interfaces de un único método podía resultar innecesaria si no existía evidencia de clientes con necesidades diferenciadas.

## Ajustes realizados

El resultado de Copilot fue revisado críticamente antes de incorporarlo a la propuesta final y posteriormente se contrastó con los anexos SRP y OCP ya integrados en `develop`, además de los casos de uso y requisitos del sistema.

Se aceptó como punto de partida la alternativa centrada en la clase `Pedido`, porque el boceto inicial permite identificar grupos de operaciones con necesidades diferentes desde la perspectiva de sus clientes.

Se realizaron los siguientes ajustes:

- Se mantuvo la agrupación de `agregarItem()`, `quitarItem()` y `modificarItem()` en una interfaz de edición denominada `IEdicionPedido`. Las tres operaciones modifican el contenido del pedido y se encuentran relacionadas con las restricciones de edición definidas para el estado recibido.

- La propuesta inicial agrupaba `cambiarEstado()` y `cancelar()` en una interfaz `ICicloVidaPedido`. Durante la revisión se detectó que esta agrupación obligaría a clientes como `Cocina`, que necesita solicitar cambios de estado durante la preparación, a depender también de `cancelar()`, aunque no utiliza esa operación. Para aplicar ISP desde la perspectiva del cliente, se reemplazó esa interfaz por `ICambioEstadoPedido`, que contiene únicamente `cambiarEstado()`.

- La operación `cancelar()` permanece en `Pedido`, pero no se incorporó a las interfaces propuestas. No se creó una interfaz adicional únicamente para contenerla, ya que no se identificó un conjunto de clientes que justificara esa abstracción y hacerlo habría introducido una fragmentación innecesaria.

- Copilot había identificado `calcularTotal()` y `registrarPago()` como responsabilidades potencialmente segregables. En una primera revisión ambas se agruparon en `ICobroPedido`, pero esta decisión fue descartada posteriormente al contrastar la propuesta ISP con los anexos SRP y OCP ya integrados en `develop`. En esos diseños, `Pedido` deja de calcular el total y registrar el pago: esas responsabilidades pasan a `CalculadoraTotalPedido` y `RegistradorPago`. Por coherencia entre los principios aplicados en el parcial, `ICobroPedido` fue eliminada de la propuesta final.

- Se incorporaron explícitamente los clientes de las interfaces en el diagrama UML para mostrar la aplicación del ISP desde el punto de vista de las dependencias. `GestorPedidos` depende de `IEdicionPedido`, mientras que `Cocina` y `Encargado` dependen de `ICambioEstadoPedido`.

- Se descartó una interfaz general como `IGestionPedido`, porque reuniría operaciones utilizadas por clientes con necesidades diferentes y generaría dependencias hacia métodos que no utilizan.

- La advertencia de Copilot sobre interfaces de un único método se revisó según el contexto concreto. Aunque una interfaz de un solo método puede ser innecesaria si no existe una necesidad diferenciada, `ICambioEstadoPedido` se mantuvo porque los clientes representados necesitan específicamente la capacidad de solicitar cambios de estado sin depender de las operaciones de edición o cancelación.

- No se agregaron nuevos métodos ni requisitos para justificar la solución. Las interfaces propuestas abstraen comportamientos ya existentes y las dependencias de los clientes se fundamentan en las responsabilidades y casos de uso documentados.

- Finalmente, se agregaron anotaciones al diagrama UML para explicitar el criterio de agrupación de cada interfaz y los requisitos asociados, y se corrigió la referencia de la imagen para permitir acceder tanto al PNG como al código PlantUML.
