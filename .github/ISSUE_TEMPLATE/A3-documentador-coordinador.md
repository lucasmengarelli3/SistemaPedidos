---
name: A3 - Documentador y Coordinador
about: Issue para documentación, coordinación, integración y revisiones de la Actividad Obligatoria N°3
title: "A3 - Documentar y coordinar repositorio"
labels: "actividad-obligatoria-3, documentador-coordinador"
---

## Descripción de la tarea

Coordinar la Actividad Obligatoria N.º 3 del Grupo N.º 2, asegurar la integración de los artefactos del equipo, mantener la documentación y navegación del repositorio, realizar revisiones de Pull Requests asistidas con GitHub Copilot y supervisar el flujo de ramas hasta la entrega.

Este Issue corresponde al rol de Documentador y Coordinador de Repositorio. Incluye tareas propias y verificaciones de actividades realizadas por otros integrantes.

## Responsable

- **Integrante:** @usuario
- **Rama de trabajo:** `feature/doc-coord-repo-update-readme-md`
- **Rama de destino:** `develop`

## Objetivos

### 1. Base del Primer Parcial

- [ ] Verificar que se resolvieron los Request Changes del Primer Parcial.
- [ ] Confirmar el LGTM y la aprobación docente.
- [ ] Confirmar el merge de `release/primer-parcial` hacia `master`.
- [ ] Coordinar el backport mediante `backport/primer-parcial`, creado desde `master` actualizado y dirigido a `develop`.
- [ ] Verificar que la PR del backport fue aprobada por otro integrante y fusionada.
- [ ] Confirmar que `develop` contiene los cambios necesarios del Primer Parcial antes de iniciar las features de A3.

### 2. Estructura y documentación

- [ ] Coordinar la creación de `diagramas/04-diagramas-actividades/`.
- [ ] Coordinar la creación de `diagramas/05-diagramas-secuencia/`.
- [ ] Verificar que existen cinco diagramas de actividades.
- [ ] Verificar que existen cinco diagramas de secuencia.
- [ ] Comprobar que cada diagrama tiene sus archivos `.puml` y `.png`.
- [ ] Verificar que los PNG corresponden a la versión final de los archivos PlantUML.
- [ ] Verificar la existencia de `diagramas/04-diagramas-actividades/diagramas_de_actividades.md`.
- [ ] Verificar la existencia de `diagramas/05-diagramas-secuencia/diagramas_de_secuencias.md`.
- [ ] Comprobar que ambos índices enlazan correctamente los diagramas.
- [ ] Actualizar `README.md` con el Grupo N.º 2, los datos de los integrantes y los enlaces a los nuevos artefactos.
- [ ] Actualizar `diagramas/diagramasUML.md` con los diagramas de actividades y secuencia.
- [ ] Verificar la coherencia y el funcionamiento de los enlaces Markdown.
- [ ] Mantener `changelog.md` actualizado con los aportes del equipo.

### 3. Issues y Pull Requests

- [ ] Verificar que cada integrante creó los Issues correspondientes.
- [ ] Comprobar que cada uno de los diez diagramas tiene un Issue asociado.
- [ ] Verificar que las ramas `feature/` se crearon desde `develop` actualizado.
- [ ] Comprobar que las ramas respetan el formato requerido.
- [ ] Revisar al menos cuatro PRs de ramas `feature/` hacia `develop`.
- [ ] Verificar que las PRs estén vinculadas con sus Issues.
- [ ] Comprobar que cada PR tenga al menos un revisor.
- [ ] Aprobar las PRs que cumplan los requisitos o solicitar correcciones cuando corresponda.
- [ ] Verificar que las integraciones se realicen mediante `Rebase and merge`.
- [ ] Verificar que `changelog.md` registre autor, rol, aporte, Issue y PR.

### 4. Code reviews asistidos con IA

Realizar y documentar al menos cuatro revisiones de Pull Requests utilizando GitHub Copilot Chat en VS Code.

Registrar la evidencia en `ia/a3/documentador-coordinador.md`.

| Revisión | PR | Autor | Estado |
| --- | --- | --- | --- |
| 1 | Pendiente | @usuario | Pendiente |
| 2 | Pendiente | @usuario | Pendiente |
| 3 | Pendiente | @usuario | Pendiente |
| 4 | Pendiente | @usuario | Pendiente |

Para cada revisión:

- [ ] Identificar la PR, el autor y el rol revisado.
- [ ] Consultar la consigna de A3 y los archivos de contexto pertinentes.
- [ ] Registrar el prompt exacto utilizado en GitHub Copilot.
- [ ] Registrar los archivos de contexto efectivamente consultados.
- [ ] Registrar el output obtenido.
- [ ] Contrastar los hallazgos con los archivos reales y la consigna.
- [ ] Documentar los hallazgos aceptados, rechazados o reformulados y sus justificaciones.
- [ ] Publicar la revisión correspondiente en GitHub.
- [ ] Registrar el enlace a la revisión y la decisión humana.
- [ ] Verificar las correcciones solicitadas cuando corresponda.

### 5. Participación técnica propia

- [ ] Crear una rama `feature/doc-coord-*` desde `develop` actualizado.
- [ ] Incorporar las actualizaciones de `README.md`.
- [ ] Incorporar las actualizaciones de `diagramas/diagramasUML.md`.
- [ ] Incorporar la documentación de IA en `ia/a3/documentador-coordinador.md`.
- [ ] Incorporar las plantillas de Issues y Pull Requests preparadas para A3, coordinando su integración para evitar conflictos con otros cambios.
- [ ] Registrar los aportes propios en `changelog.md`.
- [ ] Crear una PR hacia `develop` vinculada a este Issue mediante `Closes #X`.
- [ ] Solicitar revisión y aprobación de otro integrante antes del merge.
- [ ] Integrar la PR mediante `Rebase and merge` una vez aprobada.

### 6. Preparación de la entrega

- [ ] Confirmar que todas las features de A3 están integradas en `develop`.
- [ ] Verificar que los diez diagramas cumplen los requisitos correspondientes.
- [ ] Comprobar que todos los índices, archivos de IA y enlaces están completos.
- [ ] Crear `release/actividad-obligatoria-3` desde `develop` actualizado.
- [ ] Crear la PR de release hacia `master` utilizando la plantilla correspondiente.
- [ ] Verificar que el título de la PR respeta el formato `[GRUPO N°2][Actividad Obligatoria N°3] Entrega de la actividad`.
- [ ] Verificar que la PR de release incluye los entregables de A3.
- [ ] Limpiar las ramas remotas sobrantes, dejando únicamente `master`, `develop` y `release/actividad-obligatoria-3`.
- [ ] Entregar el enlace de la PR de release en el campus virtual.
- [ ] Compartir el enlace en el canal `#2026-2do-cuat-doo` de Slack, mencionando a `@Matias Velasquez` y a los integrantes del equipo.
- [ ] Esperar el LGTM y la autorización docente antes de fusionar la PR de release.

## Archivos involucrados

- `README.md`
- `changelog.md`
- `diagramas/diagramasUML.md`
- `diagramas/04-diagramas-actividades/diagramas_de_actividades.md`
- `diagramas/05-diagramas-secuencia/diagramas_de_secuencias.md`
- `ia/a3/documentador-coordinador.md`
- `.github/ISSUE_TEMPLATE/`
- `.github/PULL_REQUEST_TEMPLATE/`

## Criterios de finalización

- [ ] La documentación principal está actualizada.
- [ ] Los diez diagramas y sus archivos correspondientes fueron verificados.
- [ ] Los enlaces Markdown funcionan.
- [ ] Se realizaron y documentaron al menos cuatro revisiones asistidas con Copilot.
- [ ] La PR propia fue revisada, aprobada e integrada en `develop`.
- [ ] La trazabilidad de Issues, PRs y changelog está completa.
- [ ] La PR de release está preparada conforme a la consigna y fue comunicada por los canales solicitados.

## Notas para el equipo

<!-- Registrar acuerdos, dificultades, contingencias y decisiones relevantes. -->