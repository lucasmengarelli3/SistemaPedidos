# Especialista en Principios de Extensión - LSP

## Prompt utilizado

ACTUA COMO UN ESPECIALISTA EN DISEÑO ORIENTADO A OBJETOS Y ARQUITECTURA DE SOFTWARE, EN PRINCIPIO SOLID (UTILIZANDO EL PRINCIPIO DE SUSTITUCIÓN DE LISKOV). LEE LAS consignas.md DE MODO GENERAL PARA TENER UNA IDEA Y DESDE AHÍ CUMPLE LAS SIGUIENTES INSTRUCCIONES:

1) EN EL ARCHIVO anexos/principios-solid/03-lsp.md COPIA EL ARCHIVO plantilla.md
2) EVALUANDO LA INFORMACION DE anexos.md, diagramas/01-diagrama-clases/01-boceto-inicial-excalidraw y las tarjetas CRC de herramientas-agile/tarjetas-crc como contexto.
3) ANALIZA LAS JERARQUÍAS DE HERENCIA PROPUESTAS Y VERIFICA QUE LAS SUBCLASES PUEDAN SUSTITUIR A SUS SUPERCLASES SIN ALTERAR EL COMPORTAMIENTO ESPERADO. REVISÁ CRÍTICAMENTE AMBOS RESULTADOS Y AJUSTÁ LO QUE NO CORRESPONDA AL CONTEXTO DEL SISTEMA.
4) POSTERIORMENTE DENTRO DE anexos/principios-solid/03-lsp.md COMPLETA LA PLANILLA QUE COPIASTE, RESPETANDO LOS TÍTULOS Y SUBTÍTULOS Y COMPLETANDO Y SUSTITUYENDO EL DESARROLLO DE CADA UNO DE ESTOS.
5) EL DIAGRAMA QUE DEBES CREAR DEBE LLEVAR COMO NOMBRE 01-solid-03-lsp.puml y su versión exportada 01-solid-03-lsp.png. ESTE DIAGRAMA DEBE MOSTRAR TANTO EXTENSIBILIDAD SIN MODIFICACIÓN DE CÓDIGO COMO JERARQUÍAS CON SUSTITUIBILIDAD CORRECTAS Y DEBE ESTAR DENTRO DE LA CARPETA diagramas/01-diagrama-clases/

Prompt resumido:

> Analiza la jerarquía de herencia del sistema de pedidos del kiosco y aplica el Principio de Sustitución de Liskov. Verifica que las subclases puedan sustituir a las superclases sin romper el comportamiento esperado del dominio, priorizando estados del pedido y estrategias de pago. Documenta la propuesta con una explicación técnica y un diagrama UML que refleje una sustitución segura y una expansión compatible con el modelo del negocio.

## Archivos de contexto referenciados

Se consultó la consigna general de la materia y se trabajó con los siguientes artefactos de contexto:

- [anexos/anexos.md](../../anexos/anexos.md)
- [anexos/introduccion.md](../../anexos/introduccion.md)
- [diagramas/01-diagrama-clases/01-boceto-inicial.excalidraw](../../diagramas/01-diagrama-clases/01-boceto-inicial.excalidraw)
- [herramientas-agile/tarjetas-crc/tarjetas-crc.md](../../herramientas-agile/tarjetas-crc/tarjetas-crc.md)
- [anexos/principios-solid/02-ocp.md](../../anexos/principios-solid/02-ocp.md)

## Output obtenido

Se analizó la jerarquía del dominio para identificar qué relaciones de herencia eran válidas y cuáles eran meras apariencias de especialización. La conclusión principal es que el estado del pedido y la estrategia de pago sí admiten jerarquías apoyadas en contratos de comportamiento, mientras que otras relaciones no son jerarquías de sustitución reales y deben resolverse con composición o separación de responsabilidades.

## Ajustes realizados

Se revisó críticamente la propuesta inicial y se ajustó para que encaje con el contexto del proyecto:

- Se priorizó la relación `Pedido -> EstadoPedido` como una abstracción de contrato y no como una herencia de `Pedido` en cada estado.
- Se evitó considerar a `PedidoListo`, `PedidoEntregado` o `PedidoCancelado` como subclases de `Pedido`, porque eso traería varios problemas de LSP y contradicciones de negocio.
- Se validó la jerarquía de pagos como una estrategia común (`MetodoPago`) con subclases sustituibles (`Efectivo`, `Tarjeta`, `PagoQR`, `PagoPuntos`).
- Se mantuvo la idea de que el cliente solo debe depender de la superclase abstracta, no de la implementación concreta.
- Se reforzó la explicación para que quede claro que LSP no consiste en “heredar por heredar”, sino en preservar el comportamiento del contrato.

## Resultado final documentado

- Documento LSP: [anexos/principios-solid/03-lsp.md](../../anexos/principios-solid/03-lsp.md)
- Diagrama UML: [diagramas/01-diagrama-clases/01-solid-03-lsp.puml](../../diagramas/01-diagrama-clases/01-solid-03-lsp.puml)
- Exportación visual: [diagramas/01-diagrama-clases/01-solid-03-lsp.png](../../diagramas/01-diagrama-clases/01-solid-03-lsp.png)
