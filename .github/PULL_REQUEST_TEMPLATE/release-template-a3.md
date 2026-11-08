# 📦 [GRUPO N°X][Actividad Obligatoria N°3] Entrega de la actividad

> Plantilla para la Pull Request final de la Actividad Obligatoria N°3.
>
> **Rama de origen:** `release/actividad-obligatoria-3`
> **Rama de destino:** `master`
>
> **Título obligatorio de la PR:** `[GRUPO N°X][Actividad Obligatoria N°3] Entrega de la actividad`

---

## 🧾 Descripción general de la entrega

Esta Pull Request representa la entrega final de la **Actividad Obligatoria N°3 — Diseño de Diagramas de Actividades y de Secuencias**.

Incluye la integración de los aportes realizados por los cuatro integrantes del grupo, previamente revisados e incorporados en `develop`, junto con los diagramas, documentación de IA e índices correspondientes.

El trabajo se construyó sobre la base corregida del Primer Parcial y las Actividades Obligatorias N°1 y N°2.

---

## 👥 Integrantes del grupo

| Nombre completo | Rol asignado | Usuario GitHub |
| --- | --- | --- |
| Nombre 1 | Especialista en Diagramas de Actividades — Casos de Uso 1 y 2 | @usuario |
| Nombre 2 | Especialista en Diagramas de Actividades — Casos de Uso 3, 4 y 5 | @usuario |
| Nombre 3 | Especialista en Diagramas de Secuencia | @usuario |
| Nombre 4 | Documentador y Coordinador de Repositorio | @usuario |

---

## 🔗 Trazabilidad de contribuciones

| Integrante | Rol | Issue(s) | PR(s) |
| --- | --- | --- | --- |
| @usuario | Especialista en Diagramas de Actividades — CU 1 y 2 | # | # |
| @usuario | Especialista en Diagramas de Actividades — CU 3, 4 y 5 | # | # |
| @usuario | Especialista en Diagramas de Secuencia | # | # |
| @usuario | Documentador y Coordinador de Repositorio | # | # |

### Pull Requests integradas

<!-- Enumerar las PRs de A3 integradas en develop, con sus enlaces -->

- PR #
- PR #
- PR #
- PR #

---

## 📂 Entregables principales incluidos

### Documentación general
- [ ] `README.md` actualizado con enlaces a los nuevos diagramas e índices.
- [ ] `changelog.md` actualizado con los aportes de cada integrante.
- [ ] `diagramas/diagramasUML.md` actualizado con los nuevos tipos de diagramas.

### Diagramas de actividades
- [ ] `diagramas/04-diagramas-actividades/`
- [ ] `diagramas/04-diagramas-actividades/diagramas_de_actividades.md`
- [ ] Cinco diagramas de actividades en formato `.puml` y `.png`.

### Diagramas de secuencia
- [ ] `diagramas/05-diagramas-secuencia/`
- [ ] `diagramas/05-diagramas-secuencia/diagramas_de_secuencias.md`
- [ ] Cinco diagramas de secuencia en formato `.puml` y `.png`.

### Documentación del uso de IA
- [ ] `ia/a3/esp-actividades-1-2.md`
- [ ] `ia/a3/esp-actividades-3-4-5.md`
- [ ] `ia/a3/esp-secuencia.md`
- [ ] `ia/a3/documentador-coordinador.md`

---

## 🔍 Verificación técnica de los diagramas

### Diagramas de actividades

- [ ] Existen cinco diagramas de actividades correspondientes a los cinco casos de uso de A2.
- [ ] Cada diagrama tiene sus archivos `.puml` y `.png`, correctamente nombrados.
- [ ] Cada diagrama incluye al menos 10 actividades.
- [ ] Cada diagrama incluye al menos 3 swimlanes.
- [ ] Los diagramas representan decisiones, bifurcaciones, caminos alternativos, inicio y fin.
- [ ] Los actores, actividades y flujos son coherentes con los casos de uso y escenarios de A2.
- [ ] El índice `diagramas_de_actividades.md` contiene enlaces funcionales a los cinco diagramas.

### Diagramas de secuencia

- [ ] Existen cinco diagramas de secuencia correspondientes a los escenarios definidos en A2.
- [ ] Cada diagrama tiene sus archivos `.puml` y `.png`, correctamente nombrados.
- [ ] Cada diagrama incluye al menos 4 participantes.
- [ ] El primer participante, ubicado a la izquierda, representa al actor que inicia el escenario.
- [ ] Cada participante tiene al menos 3 mensajes o interacciones con otros participantes.
- [ ] Los mensajes siguen un orden cronológico y utilizan nombres en `camelCase`, con argumentos cuando corresponde.
- [ ] Se respeta la notación UML para clases (`Clase`), objetos (`:objeto`) o ambos (`Clase:objeto`).
- [ ] Se utiliza `destroy` para los objetos temporales que dejan de existir durante el escenario.
- [ ] Los participantes y mensajes son coherentes con los escenarios de A2 y las tarjetas CRC.
- [ ] El índice `diagramas_de_secuencias.md` contiene enlaces funcionales a los cinco diagramas.

---

## 🤖 Documentación del uso de IA

- [ ] Cada especialista documentó los prompts utilizados con GitHub Copilot.
- [ ] Los prompts están incluidos en bloques de código con triple comilla invertida.
- [ ] Se identificaron los archivos de contexto utilizados.
- [ ] Se documentaron los ajustes humanos y las iteraciones relevantes.
- [ ] La documentación se encuentra en el archivo correspondiente de `ia/a3/`.

### Code reviews del Documentador y Coordinador

- [ ] Se realizaron al menos cuatro revisiones de Pull Requests de ramas `feature/` hacia `develop`.
- [ ] Las cuatro revisiones se documentaron en `ia/a3/documentador-coordinador.md`.
- [ ] Cada revisión incluye el prompt utilizado en Copilot.
- [ ] Cada revisión incluye el output generado por Copilot.
- [ ] Cada revisión incluye los ajustes humanos realizados antes de publicar el comentario en GitHub.
- [ ] Las PRs fueron revisadas y aprobadas antes de su integración a `develop`.

---

## 📋 Checklist de integración y calidad

### Base del Primer Parcial
- [ ] Se resolvieron los Request Changes pendientes del Primer Parcial.
- [ ] La PR `release/primer-parcial` recibió el LGTM y Approve docente.
- [ ] La release del Primer Parcial fue integrada en `master`.
- [ ] Se realizó el backport mediante `backport/release-primer-parcial` hacia `develop`.
- [ ] La PR del backport fue aprobada por otro integrante antes del merge.

### Trabajo colaborativo
- [ ] Cada integrante creó los Issues correspondientes a sus tareas.
- [ ] Cada integrante trabajó en una rama propia con el prefijo `feature/` y naming en kebab-case.
- [ ] Las PRs de A3 fueron dirigidas hacia `develop`.
- [ ] Los Issues están vinculados a las PRs correspondientes.
- [ ] Las PRs fueron revisadas antes de su integración.
- [ ] Se utilizó `Rebase and merge` para integrar las features.
- [ ] Todas las features de A3 fueron integradas en `develop`.
- [ ] `changelog.md` registra el autor, rol, aporte, Issue y PR de cada contribución.

### Estructura y navegación
- [ ] La estructura de carpetas coincide con la consigna.
- [ ] Los archivos respetan la nomenclatura requerida.
- [ ] Los índices de diagramas de actividades y secuencia están completos.
- [ ] `diagramas/diagramasUML.md` enlaza los nuevos índices.
- [ ] `README.md` enlaza los componentes principales del proyecto.
- [ ] Todos los enlaces Markdown fueron comprobados.
- [ ] Se verificó la coherencia entre diagramas, escenarios, casos de uso, tarjetas CRC y documentación previa.
- [ ] Se revisaron la ortografía y el formato Markdown.

### Preparación de la release
- [ ] `release/actividad-obligatoria-3` fue creada desde `develop` actualizado.
- [ ] La PR tiene como origen `release/actividad-obligatoria-3` y destino `master`.
- [ ] El título de la PR respeta exactamente el formato solicitado.
- [ ] Se verificó la limpieza de ramas remotas, dejando únicamente `master`, `develop` y `release/actividad-obligatoria-3`.

---

## 📣 Comunicación y entrega

- [ ] Se entregó en el campus virtual únicamente el enlace de esta PR de release.
- [ ] Se compartió el enlace de la PR en Slack, en el canal `#2026-2do-cuat-doo`.
- [ ] Se utilizó el mismo formato de título solicitado para la PR.
- [ ] Se mencionó a @Matias Velasquez y a todos los integrantes del grupo en el hilo correspondiente.

---

## 📌 Notas adicionales para el docente

<!-- Agregar aclaraciones relevantes, dificultades, decisiones del equipo o contingencias documentadas. -->

---

**⚠️ Esta Pull Request no debe fusionarse hacia `master` hasta recibir el LGTM y el Approve formal del docente en GitHub.**