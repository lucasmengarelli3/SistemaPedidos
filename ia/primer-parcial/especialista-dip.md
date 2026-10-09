# Bitácora de IA - Especialista en Inversión de Dependencias (DIP)

## Prompt utilizado
> Con base en los archivos del proyecto que te adjunté como contexto (`anexos/introduccion.md`, `01-boceto-inicial.excalidraw` y las tarjetas CRC de `herramientas-agile/tarjetas-crc/`):
> 1. Identifica las dependencias hacia clases concretas en el diseño actual del Kiosco "Sabor", especialmente en `Pedido`, `Pago`, `PersonalAtencion` y `Cocina`.
> 2. Propón abstracciones (interfaces o clases abstractas) para invertirlas aplicando el Principio de Inversión de Dependencias (DIP).
> 3. Indica dónde aplicar Inyección de Dependencias por constructor.
> 4. Genera el contenido para el anexo `anexos/principios-solid/05-dip.md` en Markdown conceptual, sin código Java.
> 5. Genera el código PlantUML para el diagrama de clases refactorizado `diagramas/01-diagrama-clases/01-solid-05-dip.puml`.
> 
> Respeta el dominio del Kiosco "Sabor" y los nombres de métodos y atributos de las tarjetas CRC oficiales.

## Archivos de contexto referenciados
- [`anexos/introduccion.md`](../../anexos/introduccion.md)
- [`diagramas/01-diagrama-clases/01-boceto-inicial-corregido.excalidraw`](../../diagramas/01-diagrama-clases/01-boceto-inicial-corregido.excalidraw)
- [`herramientas-agile/tarjetas-crc/tarjetas-crc.md`](../../herramientas-agile/tarjetas-crc/tarjetas-crc.md)
- Tarjetas CRC individuales (`PersonalAtencion`, `Cocina`, `Pedido`, `ItemPedido`, `Producto`, `Personalizacion`, `Pago`, `Encargado`, `Cliente`) en `herramientas-agile/tarjetas-crc/`

## Output obtenido
- Texto borrador para el anexo conceptual de DIP en Markdown.
- Código PlantUML para el diagrama de clases refactorizado con las abstracciones propuestas (`IRepositorioPedidos`, `ICatalogoProductos`, `IRecepcionPedidos`, `IProcesadorPago`).
- Matriz de Inyección de Dependencias por constructor para `PersonalAtencion`, `Cocina` y `RegistradorPago`.
- La imagen del diagrama (`01-solid-05-dip.png`) se generó y exportó directamente desde VS Code utilizando la extensión de PlantUML.

## Ajustes realizados
- **Reorganización de secciones:** Se adaptó el anexo conceptual para responder estrictamente a la estructura de 5 encabezados exigida por la consigna (`Propósito y Tipo del Principio SOLID`, `Motivación`, `Explicación de Clases Abstractas e Interfaces`, `Estructura de Clases`, `Justificación Técnica`).
- **Inclusión teórica:** Se agregó la explicación explícita sobre la diferencia entre clases abstractas e interfaces y la fundamentación de por qué se eligieron interfaces para las abstracciones del sistema.
- **Alineación de clases con SRP/OCP:** Se unificó la lógica de cobro reemplazando la clase `GestorPago` por `RegistradorPago`, alineando el modelo con los anexos previos de SRP y OCP, y eliminando firmas duplicadas de `registrarPago()` en `Pedido` y `Pago`.
- **Correcciones de notación UML:** Se corrigió la declaración del tipo numerado `ResultadoPago` para usar la sintaxis `enum` nativa de PlantUML con sus literales (`APROBADO`, `RECHAZADO`), y se especificó el tipo genérico explícito `List<Pedido>` en la interfaz `IRepositorioPedidos`.
- **Premisa sobre el diseño inicial:** Se descartó la afirmación de que el boceto ya tenía clases concretas de persistencia o cobro. Las tarjetas CRC no las incluyen, por lo que los repositorios y procesadores se documentaron como puntos de extensión propuestos, y el anexo conserva la tabla de dependencias por clase y la matriz de inyección por constructor.
