## Trazabilidad de Prompts de Generación Inicial con IA y Criterio de Evaluación Humana

Como parte de la evidencia del proceso de desarrollo, se documentan los prompts originales estructurados y enviados al asistente de IA en Visual Studio Code para la generación inicial de los diagramas PlantUML de la Actividad A3. 

> **Criterio de Evaluación Humana:** Cada diagrama generado por el asistente fue auditado de forma iterativa bajo los siguientes parámetros de calidad académica y técnica:
> 1. **Fidelidad al dominio:** Coherencia estricta con las tarjetas CRC y las especificaciones funcionales de los casos de uso del sistema.
> 2. **Rigurosidad sintáctica:** Uso correcto de las directrices de PlantUML (delimitadores limpios, visibilidad de actores a la izquierda, notación de objetos como `Clase:objeto` y mensajes estructurados en `camelCase` con paso explícito de parámetros).
> 3. **Consistencia estructural:** Inclusión adecuada de estructuras de control (`alt`, `opt`, `loop`) y control formal del ciclo de vida de objetos temporales mediante `create` y `destroy`.

### 1. Registrar Pedido (`05-secuencia-registrar-pedido-flujo-principal-01.puml`)
* **Prompt de generación inicial:**
  > *"Actúa como un especialista en modelado UML. A partir de las tarjetas CRC y el caso de uso de Registrar Pedido, genera el código PlantUML completo para el flujo principal exitoso. Debe incluir como participantes al Usuario de mostrador, Cliente, PantallaPedidos, PersonalAtencion, CatalogoProductos, Producto, ItemPedido, Personalizacion, Pedido y Cocina. Utiliza autonumber, oculta el footbox y aplica un skinparam limpio sin sombras. El flujo debe contemplar la selección del catálogo, el ingreso del pedido con sus ítems, la validación de disponibilidad, la creación de ítems con sus personalizaciones opcionales, el cálculo de totales mediante un resumen temporal y la notificación final a cocina."*

### 2. Modificar Pedido (`05-secuencia-modificar-pedido-flujo-principal-03.puml`)
* **Prompt de generación inicial:**
  > *"Diseña el diagrama de secuencia en PlantUML para el flujo principal de Modificación de Pedido. Partiendo de los datos de entrada del Usuario de mostrador, el sistema debe buscar el pedido por ID, validar su estado actual mediante una SolicitudModificacion, aplicar los cambios requeridos sobre los ítems y productos consultando precios y disponibilidad, recalcular el subtotal y el total nuevo, mostrar el resumen de cambios para confirmación y notificar finalmente a cocina y al usuario."*

### 3. Preparar Pedido (`05-secuencia-preparar-pedido-flujo-principal-05.puml`)
* **Prompt de generación inicial:**
  > *"Genera el código PlantUML para el escenario de Preparación de Pedido con el operador de Cocina como actor principal. El diagrama debe cubrir tres bloques secuenciales: 1) Consultar la cola de pedidos recibidos ordenados por prioridad; 2) Seleccionar el pedido, consultar sus detalles, ítems y personalizaciones; 3) Iniciar la preparación cambiando el estado del pedido con su respectiva validación y transición, hasta completar los productos preparados, marcar el pedido como listo y notificar al mostrador."*

### 4. Cobrar Cuenta (`05-secuencia-cobrar-cuenta-flujo-principal-07.puml`)
* **Prompt de generación inicial:**
  > *"Crea el diagrama de secuencia en PlantUML para el escenario de Cobrar Cuenta de un pedido. El flujo debe involucrar al Cliente, Usuario de mostrador, SistemaCobro, Pedido, MedioPago, SolicitudAutorizacion y Pago. Debe representar la selección del medio de pago, la validación del total vigente, la preparación de la autorización, la consulta de disponibilidad en el medio de pago externo y la bifurcación (alt) entre un pago aprobado (generando el registro de pago y emitiendo el comprobante) y un pago rechazado."*

### 5. Entregar Pedido (`05-secuencia-entregar-pedido-flujo-principal-09.puml`)
* **Prompt de generación inicial:**
  > *"Genera el diagrama PlantUML correspondiente a Entregar Pedido. Utiliza como actor principal humano al Usuario de mostrador (distinguiéndolo de las clases de control) y al Cliente. El proceso debe iniciar informando los datos de retiro, validando la coincidencia del número y referencia mediante una clase de consulta y el Pedido, mostrando el estado listo, registrando la entrega de forma exitosa o contemplando el flujo alternativo de verificación adicional con el encargado si la validación falla."*

### 6. Cancelar Pedido (`05-secuencia-cancelar-pedido-flujo-excepcion-03.puml`)
* **Prompt de generación inicial:**
  > *"Elabora el diagrama de secuencia PlantUML para el caso de Cancelación de Pedido (flujo y excepciones). Debe estructurarse con la participación del Usuario de mostrador, Cliente, InterfazCancelacion, Pedido, Cocina y un objeto temporal SolicitudCancelacion. El diagrama debe evidenciar la búsqueda del pedido, la solicitud y validación de cancelación, el flujo condicional (alt) según sea cancelable o no (notificando a cocina si está en preparación), manejando explícitamente el ciclo de vida del objeto temporal mediante las sentencias create y destroy."*