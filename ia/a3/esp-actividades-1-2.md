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

- A continuación, se muestra un fragmento representativo del output original para CU1 devuelto por la herramienta antes de las correcciones manuales:

@startuml
title Diagrama de Actividad - CU1: Registrar Pedido

|Usuario de Mostrador|
start
:Iniciar nuevo pedido;
:Solicitar catálogo de productos;

|Sistema|
:Mostrar catálogo disponible;
:Calcular precios vigentes;

|Usuario de Mostrador|
:Agregar productos y cantidades;
:Agregar personalizaciones;
:Ingresar referencia de retiro;

|Sistema|
:Validar datos del pedido;
if (¿Datos válidos?) then (No)
  :Corregir datos del pedido;
else (Sí)
  :Datos validados correctamente;
endif

|Usuario de Mostrador|
:Confirmar pedido;

|Sistema|
:Generar identificador único;
:Guardar pedido en estado "recibido";
stop
@enduml

- Output Original para CU2 antes de las correcciones manuales: 

@startuml
title Diagrama de Actividad - CU2: Modificar Pedido

|Usuario de Mostrador|
start
:Buscar pedido por identificador;
:Solicitar modificación;

|Sistema|
:Mostrar pedido;
:Verificar estado del pedido;

|Usuario de Mostrador|
:Agregar o quitar productos;
:Modificar personalizaciones;

|Sistema|
:Validar disponibilidad;
:Recalcular total;

|Usuario de Mostrador|
:Confirmar cambios;

|Sistema|
:Persistir cambios;
stop
@enduml

## Iteraciones relevantes

- Iteración 1: El primer output de la IA generó los diagramas con los flujos lógicos, pero se notó que no incluía el camino alternativo para cuando un producto no está disponible en el CU1. Se le solicitó a la IA que lo agregue.

- Iteración 2: Se revisó que los bucles de validación estuvieran correctamente representados. La IA los incluyó, pero se ajustó manualmente la sintaxis para que el flujo de retorno fuera claro (usando repeat y backward).

- Iteración 3 (ajustes finales): Se ordenó el flujo del CU2 para que la confirmación del usuario ocurra después de que el sistema recalcule el total, tal como indica el escenario de la Actividad 2.

## Ajustes realizados
- Se revisó manualmente que el carril de "Cocina" refleje correctamente la recepción asíncrona de la comanda.

- Se implementaron bucles de validación en ambos diagramas para que, si los datos/reglas no son válidos, el flujo vuelva a validar antes de continuar.

- Se ajustaron los nombres de los nodos de decisión para que reflejen exactamente las reglas de negocio (por ejemplo, en el CU2 se verifica explícitamente si el estado es "recibido").

- Se adaptó la nomenclatura de las actividades para que coincida palabra por palabra con los pasos descritos en los escenarios de la Actividad 2, garantizando la trazabilidad.

- Se corrigió el orden de las actividades en el CU2 para que la confirmación sea el último paso antes de persistir los cambios.