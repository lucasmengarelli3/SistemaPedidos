# Especialista en escenarios de casos de uso

## Prompt de trabajo

Actuar como analista de requerimientos experto en modelado de casos de uso y elicitación de escenarios. Leer `anexos/introduccion.md`, seleccionar al menos cinco casos de uso relevantes de la Actividad Obligatoria N.° 1 y documentar uno o más escenarios por caso, incluyendo flujo principal y, cuando corresponda, flujo alternativo o de excepción. Cada escenario debe usar exactamente la plantilla markdown con los campos: nombre del escenario, nombre del caso de uso, ID única, área, actor(es), descripción, activar evento, tipo de señal, pasos desempeñados/información para los pasos, precondiciones, poscondiciones, suposiciones, reunir requerimientos, aspectos sobresalientes, prioridad y riesgo. Los pasos deben ser numerados, lógicos y coherentes con el dominio; prioridad y riesgo deben incluir una justificación. Finalmente se debe realizar una revisión crítica de coherencia, actores, estados, precondiciones, poscondiciones, identificadores, áreas, prioridad y riesgo.

## Archivos referenciados

- [Introducción, requisitos y casos de uso](../../anexos/introduccion.md)
- [Tarjetas CRC](../../herramientas-agile/tarjetas-crc/tarjetas-crc.md)
- [Boceto inicial de clases](../../diagramas/01-diagrama-clases/01-boceto-inicial.excalidraw)
- [Índice de escenarios](../../diagramas/03-escenarios-casos-de-uso/escenarios_de_casos_de_uso.md)

## Selección realizada

Se seleccionaron seis casos de uso para cubrir el ciclo de vida del pedido y actores distintos:

| Caso de uso | Requisitos relacionados | Actor principal | Motivo |
| --- | --- | --- | --- |
| Registrar pedido | RF1, RF2, RF3, RF5 | Usuario de mostrador | Inicia el ciclo y fija la trazabilidad del pedido. |
| Modificar pedido | RF10, RF11, RF12 | Usuario de mostrador | Cubre cambios de productos y personalizaciones antes de cocina. |
| Preparar pedido | RF5, RF7 | Cocina | Representa la coordinación entre mostrador y cocina. |
| Cobrar cuenta | RF4 | Usuario de mostrador | Registra una operación económica y su comprobante. |
| Entregar pedido | RF2, RF7, RF13 | Usuario de mostrador / Cliente | Valida identidad de retiro y cierra el ciclo operativo. |
| Cancelar pedido | RF8, RNF4 | Usuario de mostrador | Modela la baja lógica y la conservación del historial. |

## Ajustes realizados

- Se reemplazó la ambigüedad de “entregar pedido” por una validación explícita de número, referencia, estado `listo` y registro de entrega.
- Se mantuvieron los estados definidos en la introducción y se bloquearon modificaciones fuera de `recibido`.
- Se aclaró que cancelar no elimina físicamente el pedido: lo lleva a `cancelado`, lo retira de activos y conserva su historial.
- Se incorporó el recálculo del total y la conservación del precio histórico del ítem luego de modificar un pedido.
- Se separaron los actores: mostrador registra, modifica, cobra, entrega y cancela; cocina actualiza la preparación; cliente aporta la referencia y recibe el pedido.
- Se eliminaron IDs duplicados: cada escenario tiene un ID única entre 1 y 12.
- Se justificaron prioridad y riesgo según impacto operativo, integridad de datos, dinero, trazabilidad y dependencia entre mostrador y cocina.

## Revisión crítica

Los doce escenarios están enlazados desde el [índice](../../diagramas/03-escenarios-casos-de-uso/escenarios_de_casos_de_uso.md), tienen un único caso de uso, actores compatibles y pasos numerados con información para cada paso. Las excepciones verifican catálogo no disponible, estados no editables, pedido inexistente, pago rechazado, datos de retiro inconsistentes y cancelación fuera de la ventana permitida. Las precondiciones garantizan que el flujo pueda iniciarse y las poscondiciones expresan el resultado o la ausencia de cambios cuando la operación falla.
