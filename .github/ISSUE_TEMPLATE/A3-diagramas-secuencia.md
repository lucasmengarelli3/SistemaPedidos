---
name: A3 - Diagrama de Secuencia
about: Issue individual para un diagrama de secuencia de la Actividad Obligatoria N°3
title: "A3 - Diagrama de secuencia - [caso de uso y escenario]"
labels: "actividad-obligatoria-3, esp-secuencia"
---

## Descripción de la tarea

Crear un diagrama de secuencia UML correspondiente a un escenario de caso de uso definido en la Actividad Obligatoria N°2.

El diagrama debe desarrollarse en PlantUML, exportarse a PNG y representar las interacciones entre actores y objetos en orden cronológico.

**Este Issue corresponde a un único diagrama de secuencia.**

## Identificación del escenario

- **Caso de uso:**
- **Nombre del escenario:**
- **ID del escenario:**
- **Tipo de flujo:** Principal / Alternativo / Excepción
- **Responsable:** @usuario
- **Rama de trabajo:** `feature/esp-secuencia-*`

## Archivos de referencia

- `diagramas/02-casos-de-uso/`
- `diagramas/03-escenarios-casos-de-uso/`
- `herramientas-agile/tarjetas-crc/`
- `anexos/introduccion.md`

<!-- Agregar las rutas exactas de los archivos utilizados como contexto. -->

## Objetivos

- [ ] Seleccionar un escenario documentado en A2.
- [ ] Identificar los actores, objetos y clases participantes.
- [ ] Crear el diagrama de secuencia en PlantUML.
- [ ] Incluir al menos 4 participantes.
- [ ] Ubicar al actor iniciador como primer participante, a la izquierda.
- [ ] Representar al menos 3 interacciones por participante.
- [ ] Utilizar nombres de mensajes en `camelCase`.
- [ ] Incluir argumentos en los mensajes cuando corresponda.
- [ ] Respetar la notación UML de clases (`Clase`), objetos (`:objeto`) y combinaciones (`Clase:objeto`).
- [ ] Representar la destrucción de objetos temporales con `destroy`, cuando corresponda.
- [ ] Respetar el orden cronológico de los mensajes.
- [ ] Mantener coherencia con los escenarios de A2 y las tarjetas CRC.
- [ ] Exportar el diagrama a PNG.
- [ ] Verificar que el PNG corresponda a la última versión del `.puml`.

## Archivos generados

**Carpeta:** `diagramas/05-diagramas-secuencia/`

- [ ] `05-secuencia-nombre-caso-uso-nombre-escenario-NN.puml`
- [ ] `05-secuencia-nombre-caso-uso-nombre-escenario-NN.png`

<!-- Reemplazar los nombres y NN por los valores correspondientes. -->

## Índice de diagramas

- [ ] Agregar el diagrama a `diagramas/05-diagramas-secuencia/diagramas_de_secuencias.md`.
- [ ] Incluir enlaces a los archivos `.puml` y `.png`.
- [ ] Verificar que el índice contenga cinco diagramas al finalizar la actividad.
- [ ] Comprobar que todos los enlaces funcionan.

## Uso de GitHub Copilot

- [ ] Consultar los escenarios de A2 y las tarjetas CRC como contexto.
- [ ] Registrar el prompt utilizado en un bloque de código.
- [ ] Registrar los archivos de contexto consultados.
- [ ] Registrar el output generado.
- [ ] Documentar los ajustes humanos y las iteraciones relevantes.
- [ ] Actualizar `ia/a3/esp-secuencia.md`.

## Integración y control de calidad

- [ ] Crear la rama `feature/` desde `develop` actualizado.
- [ ] Verificar que el código PlantUML se renderiza correctamente.
- [ ] Comprobar que el diagrama cumple los requisitos de la consigna.
- [ ] Registrar el aporte en `changelog.md`.
- [ ] Abrir una PR hacia `develop`.
- [ ] Vincular la PR con este Issue mediante `Closes #X`.
- [ ] Solicitar revisión al Documentador y Coordinador.
- [ ] Integrar mediante `Rebase and merge` una vez aprobada la PR.

## Notas adicionales

<!-- Registrar aclaraciones, dificultades o decisiones de modelado. -->