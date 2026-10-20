# Principio de Segregación de Interfaces (ISP)

## Propósito y Tipo del Principio SOLID

El Principio de Segregación de Interfaces (ISP) es uno de los principios SOLID y tiene como propósito reducir dependencias innecesarias entre los clientes y las interfaces que utilizan. Su regla central establece que ningún cliente debería verse obligado a depender de métodos que no necesita.

El principio busca evitar las denominadas interfaces "gordas" o poco especializadas, que reúnen operaciones correspondientes a distintos propósitos y fuerzan a sus clientes o clases implementadoras a depender de funcionalidades ajenas a su responsabilidad.

Para evitar este problema, ISP propone diseñar interfaces cohesivas y especializadas, agrupando operaciones que se utilizan juntas y separando aquellas que responden a responsabilidades diferentes. De esta manera, cada cliente puede depender únicamente del contrato que necesita, disminuyendo el acoplamiento y facilitando el mantenimiento y la evolución del sistema.

## Motivación

En el boceto inicial del sistema, la clase `Pedido` concentra operaciones correspondientes a distintos aspectos de la gestión de un pedido. Entre ellas se encuentran la edición de sus ítems (`agregarItem()`, `quitarItem()` y `modificarItem()`), el cambio de su estado (`cambiarEstado()`) y la cancelación (`cancelar()`).

La presencia de estos métodos en una misma clase concreta no constituye por sí sola una violación del Principio de Segregación de Interfaces. El ISP se centra en las dependencias de los clientes respecto de las operaciones expuestas por un contrato.

El problema surgiría si todas las capacidades de `Pedido` se expusieran mediante una única interfaz general, por ejemplo `IGestionPedido`. En ese caso, una clase como `Cocina`, que necesita solicitar cambios de estado durante la preparación, también dependería de operaciones de edición o cancelación que no utiliza. El caso de uso Preparar pedido establece precisamente que Cocina actualiza el pedido a en preparación y luego a listo.

Para evitar esta dependencia innecesaria, se proponen dos contratos especializados: `IEdicionPedido`, que agrupa las operaciones destinadas a modificar el contenido del pedido, e `ICambioEstadoPedido`, que expone únicamente la operación `cambiarEstado()`.

Esta separación permite que cada cliente dependa solamente de la capacidad que necesita. `GestorPedidos` utiliza el contrato de edición, mientras que `Cocina` y `Encargado` utilizan el contrato de cambio de estado.

La operación `cancelar()` permanece en `Pedido`, pero no se incorpora a estas interfaces porque los clientes identificados para los contratos propuestos no requieren conjuntamente esa operación. De esta manera se evita ampliar artificialmente una interfaz y obligar a sus clientes a depender de métodos que no utilizan.

La propuesta también se mantiene coherente con la aplicación del SRP ya incorporada al diseño del parcial. Las responsabilidades de cálculo del total y registro del pago fueron separadas de `Pedido` en `CalculadoraTotalPedido` y `RegistradorPago`, por lo que tampoco se incluyen dentro de las interfaces implementadas por `Pedido` en esta propuesta de ISP.

## Explicación de Interfaces

En diseño orientado a objetos, una interfaz representa un contrato que define un conjunto de operaciones disponibles para sus clientes. Especifica qué servicios o comportamientos pueden utilizarse, sin exponer los detalles internos de cómo se implementan.

En una interfaz explícita, como las que pueden representarse mediante la construcción `interface` en lenguajes orientados a objetos, se declaran las operaciones que las clases concretas se comprometen a implementar. De esta manera, se separa la especificación del comportamiento de su implementación concreta.

En el contexto del Principio de Segregación de Interfaces, el concepto de interfaz también puede entenderse en un sentido más general como el conjunto de operaciones públicas que una clase o módulo expone a sus clientes. El ISP establece que esos clientes no deberían depender de operaciones que no utilizan.

Por este motivo, las interfaces deben diseñarse de forma cohesiva y especializada, agrupando únicamente operaciones que responden a una misma necesidad de sus clientes.

En SistemaPedidos se proponen dos contratos especializados sobre responsabilidades que `Pedido` conserva en el diseño: `IEdicionPedido`, que reúne las operaciones de modificación del contenido, e `ICambioEstadoPedido`, que expone la operación necesaria para solicitar un cambio de estado.

De esta forma, `GestorPedidos` puede depender únicamente del contrato de edición, mientras que `Cocina` y `Encargado` pueden depender del contrato de cambio de estado. La operación `cancelar()` continúa formando parte de `Pedido`, pero no se incorpora a estos contratos porque no es requerida conjuntamente por los clientes representados en el diagrama.

## Estructura de Clases

El siguiente diagrama UML representa la aplicación del Principio de Segregación de Interfaces sobre la clase `Pedido`, considerando las responsabilidades que conserva luego de la aplicación del SRP.

Se proponen dos interfaces especializadas:

- `IEdicionPedido`, que agrupa las operaciones de modificación del contenido del pedido.
- `ICambioEstadoPedido`, que expone únicamente la operación necesaria para solicitar un cambio de estado.

La clase `Pedido` implementa ambos contratos. El diagrama también muestra los clientes que dependen de cada interfaz: `GestorPedidos` utiliza `IEdicionPedido`, mientras que `Cocina` y `Encargado` utilizan `ICambioEstadoPedido`.

La operación `cancelar()` permanece en `Pedido`, pero no forma parte de las interfaces propuestas, ya que no es una necesidad compartida por los clientes representados.

[![Diagrama UML de aplicación del ISP](../../diagramas/01-diagrama-clases/01-solid-04-isp.png)](../../diagramas/01-diagrama-clases/01-solid-04-isp.png)

- [Ver código fuente del diagrama PlantUML](../../diagramas/01-diagrama-clases/01-solid-04-isp.puml)

## Justificación Técnica

El diagrama UML propuesto muestra a la clase `Pedido` implementando dos interfaces especializadas: `IEdicionPedido` e `ICambioEstadoPedido`.

`IEdicionPedido` agrupa `agregarItem()`, `quitarItem()` y `modificarItem()`. Estas operaciones comparten una misma finalidad: modificar el contenido del pedido. En el diseño refactorizado, `GestorPedidos` es el cliente que necesita esta capacidad, por lo que puede depender únicamente de la interfaz de edición sin conocer operaciones relacionadas con cambios de estado o cancelación.

`ICambioEstadoPedido` contiene únicamente `cambiarEstado()`. Esta operación representa la capacidad necesaria para solicitar una transición del pedido. `Cocina` utiliza esta capacidad durante el caso de uso Preparar pedido, al actualizar el pedido a estado en preparación y luego a listo. `Encargado` también requiere solicitar cambios de estado, por lo que ambos clientes pueden depender del mismo contrato especializado.

La operación `cancelar()` permanece como comportamiento de `Pedido`, pero no se incorpora a `ICambioEstadoPedido`. La cancelación constituye una operación distinta y no es utilizada por todos los clientes que requieren cambios de estado. Incluirla en esa interfaz obligaría, por ejemplo, a `Cocina` a depender de un método que no necesita, contradiciendo el objetivo del ISP.

Esta separación permite observar concretamente la aplicación del principio desde la perspectiva de los clientes. Si todas las capacidades de `Pedido` se agruparan en una única interfaz general, clases como `Cocina` quedarían acopladas también a operaciones de edición o cancelación que no forman parte de su función. Con las interfaces segregadas, cada cliente conoce únicamente el contrato necesario para cumplir su responsabilidad.

La clase `Pedido` conserva las operaciones de edición, cambio de estado y cancelación, mientras que las responsabilidades de cálculo del total y registro del pago no forman parte de las interfaces propuestas. Esta decisión mantiene la coherencia con la aplicación del SRP ya incorporada al diseño del parcial, donde el cálculo del total se asigna a `CalculadoraTotalPedido` y el registro del pago a `RegistradorPago`.

Las interfaces propuestas no agregan nuevas responsabilidades al dominio, sino que abstraen capacidades ya presentes en el diseño y las exponen mediante contratos específicos. De esta manera, se evita una interfaz "gorda", se reducen dependencias innecesarias y se mantiene la cohesión entre las operaciones que cada cliente utiliza.
