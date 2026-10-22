# Registro de Interacciones y Prompts — Diagramas de Secuencia (Actividad A3)

## 1. Objetivo de la Actividad
Diseñar, estructurar, generar y exportar los diagramas de secuencia UML en código PlantUML (`.puml`) junto con sus respectivas imágenes (`.png`) para los **6 escenarios** del sistema de pedidos, cumpliendo estrictamente con los estándares de la cátedra (notación de clases/objetos, mensajes en `camelCase` con argumentos, uso correcto de estructuras de control y gestión de objetos temporales mediante `create` y `destroy`).

## 2. Herramientas y Asistencia de IA
- **Asistente utilizado:** GitHub Copilot / Gemini para la traducción de los escenarios de casos de uso y tarjetas CRC a sintaxis formal PlantUML.
- **Entorno de trabajo:** Visual Studio Code con extensiones para renderizado de PlantUML y control de versiones con Git en rama dedicada (`feature/a3-uml-secuencia`).

## 3. Escenarios Abordados y Artefactos Generados
1. **Registrar pedido** (`05-secuencia-registrar-pedido-flujo-principal-01.puml` / `.png`)
2. **Modificar pedido** (`05-secuencia-modificar-pedido-flujo-principal-03.puml` / `.png`)
3. **Preparar pedido** (`05-secuencia-preparar-pedido-flujo-principal-05.puml` / `.png`)
4. **Cobrar cuenta** (`05-secuencia-cobrar-cuenta-flujo-principal-07.puml` / `.png`)
5. **Entregar pedido** (`05-secuencia-entregar-pedido-flujo-principal-09.puml` / `.png`)
6. **Cancelar pedido** (`05-secuencia-cancelar-pedido-flujo-excepcion-03.puml` / `.png`)

## 4. Estructura de Prompts Utilizados
Para mantener la consistencia en todos los diagramas, se utilizó una estrategia de prompting estructurada basada en roles y restricciones técnicas:
- **Rol:** Especialista en Diagramas de Secuencia UML.
- **Contexto de entrada:** Escenarios detallados de casos de uso y tarjetas CRC de cada módulo.
- **Restricciones técnicas aplicadas:**
  - Delimitación limpia con `@startuml` y `@enduml`.
  - Mínimo de 4 participantes con el actor principal ubicado a la izquierda.
  - Uso riguroso de notación UML (`Clase:objeto` o `:objeto`).
  - Mensajes definidos estrictamente en `camelCase` incluyendo parámetros y argumentos relevantes.
  - Incorporación explícita de bloques alternativos (`alt`/`else`, `opt`) y el ciclo de vida de objetos temporales mediante `create` y `destroy`.