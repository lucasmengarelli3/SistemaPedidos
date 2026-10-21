# Documentación de IA - Diagramas de Actividades CU1 y CU2

## Prompt utilizado
```text 
- Actúa como un experto en modelado UML y PlantUML. Necesito que generes el código para dos diagramas de actividades basándote estrictamente en los archivos de contexto que te adjunto. Requisitos técnicos obligatorios para ambos diagramas: utilizar la sintaxis de Plantuml con swimlanes, crear un mínimo de 3 carriles con el nombre de "Usuario de Mostrador", "Sistema" y "Cocina", incluir un mínimo de 10 actividades claramente representadas con nombres descriptivos y conectadas lógicamente, utilizar nodos de decisión (rombos con if/else) para representar validaciones, marcar claramente el inicio (start) y el fin (stop) del flujo.
```

## Archivos de contexto referenciados
Para que la IA pueda generar los diagramas correctamente, se le proporcionaron los artefactos generados en la Actividad 2:

- diagramas/02-casos-de-uso/02-registrar-pedido.puml

- diagramas/03-escenarios-casos-de-uso/03-registrar-pedido-flujo-principal.md

- diagramas/02-casos-de-uso/02-modificar-pedido.puml

- diagramas/03-escenarios-casos-de-uso/03-modificar-pedido-flujo-principal.md


## Output obtenido
- La IA generó una propuesta inicial de los dos diagramas en código PlantUML, estructurando los flujos con los carriles solicitados y agregando los nodos de decisión correspondientes a las validaciones de los escenarios.


## Ajustes realizados
- Se revisó manualmente que el carril de "Cocina" refleje correctamente la recepción asíncrona de la comanda.

- Se ajustaron los nombres de los nodos de decisión para que reflejen exactamente las reglas de negocio (por ejemplo, en el CU2 se verifica explícitamente si el estado es "recibido").

- Se adaptó la nomenclatura de las actividades para que coincida palabra por palabra con los pasos descritos en los escenarios de la Actividad 2, garantizando la trazabilidad.