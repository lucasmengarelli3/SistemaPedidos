# Documentador y Coordinador de Repositorio — Uso de IA en A3

## Actividad

Actividad Obligatoria N.º 3 — Diagramas de Actividades y Diagramas de Secuencia.

**Rol:** Documentador y Coordinador de Repositorio
**Grupo:** 2
**Herramienta de IA:** GitHub Copilot Chat (modo Agent, desde VS Code)

## Objetivo

Documentar el uso de GitHub Copilot para asistir en la revisión de al menos cuatro Pull Requests de ramas `feature/` hacia `develop`, verificando el cumplimiento de la consigna, la coherencia con los artefactos anteriores y la calidad de la documentación.

Las sugerencias generadas por IA serán contrastadas con los archivos reales antes de publicar comentarios o emitir una decisión de revisión.

## Criterios generales de revisión

- Cumplimiento de los requisitos específicos del rol.
- Coherencia con los casos de uso y escenarios de A2.
- Coherencia con las tarjetas CRC, cuando corresponda.
- Cantidad mínima de actividades, swimlanes, participantes e interacciones, según el tipo de diagrama.
- Uso correcto de la notación UML.
- Correspondencia entre archivos `.puml` y `.png`.
- Nombres y rutas de archivos exigidos por la consigna.
- Funcionamiento de los enlaces Markdown.
- Actualización de `changelog.md`.
- Documentación de IA correspondiente al rol.
- Vinculación de Issues y Pull Requests.

---

## Revisión 1

**PR:** [#190 — Diagramas de actividades CU 3, 4, 5 y 6](https://github.com/lucasmengarelli3/SistemaPedidos/pull/190)  
**Autor:** @lucasmengarelli3  
**Rol revisado:** Especialista en Diagramas de Actividades — Casos de uso 3, 4 y 5 (incluye CU 6 adicional)  
**Fecha:** 21/10/2026  
**Estado:** Revisión publicada. Correcciones solicitadas, pendientes de verificar.

### Archivos de contexto

Se utilizaron los archivos del PR #190 y los artefactos originales de A2.

**Casos de uso:**
- `diagramas/02-casos-de-uso/02-preparar-pedido.puml`
- `diagramas/02-casos-de-uso/02-cobrar-cuenta.puml`
- `diagramas/02-casos-de-uso/02-entregar-pedido.puml`
- `diagramas/02-casos-de-uso/02-cancelar-pedido.puml`

**Escenarios:**
- `diagramas/03-escenarios-casos-de-uso/03-preparar-pedido-flujo-principal-pedido-listo-05.md`
- `diagramas/03-escenarios-casos-de-uso/03-preparar-pedido-flujo-excepcion-pedido-inexistente-06.md`
- `diagramas/03-escenarios-casos-de-uso/03-cobrar-cuenta-flujo-principal-cobro-aprobado-07.md`
- `diagramas/03-escenarios-casos-de-uso/03-cobrar-cuenta-flujo-alternativo-pago-rechazado-08.md`
- `diagramas/03-escenarios-casos-de-uso/03-entregar-pedido-flujo-principal-entrega-validada-09.md`
- `diagramas/03-escenarios-casos-de-uso/03-entregar-pedido-flujo-alternativo-datos-no-coinciden-10.md`
- `diagramas/03-escenarios-casos-de-uso/03-cancelar-pedido-flujo-principal-cancelacion-autorizada-11.md`
- `diagramas/03-escenarios-casos-de-uso/03-cancelar-pedido-flujo-excepcion-estado-no-cancelable-12.md`

**Archivos revisados del PR:**
- `diagramas/04-diagramas-actividades/04-actividad-preparar-pedido-03.puml`
- `diagramas/04-diagramas-actividades/04-actividad-cobrar-cuenta-04.puml`
- `diagramas/04-diagramas-actividades/04-actividad-entregar-pedido-05.puml`
- `diagramas/04-diagramas-actividades/04-actividad-cancelar-pedido-06.puml`
- Los cuatro archivos `.png` correspondientes.
- `diagramas/04-diagramas-actividades/diagramas_de_actividades.md`
- `ia/a3/esp-actividades-3-4-5.md`
- `changelog.md`

### Prompt utilizado

Se utilizó GitHub Copilot Chat en modo Agent. Primero se verificó que pudiera acceder a los archivos del PR. Luego se envió el siguiente prompt para realizar la revisión técnica:

```text
Actuá como revisor técnico del Pull Request #190 del repositorio `lucasmengarelli3/SistemaPedidos`, que incorpora diagramas de actividades para los casos de uso prepararPedido, cobrarCuenta, entregarPedido y cancelarPedido.

Realizá una revisión técnica de solo lectura. No modifiques archivos, no ejecutes comandos que alteren el repositorio, no publiques comentarios, no apruebes ni hagas merge.

**Contexto obligatorio:**
- Consultá los archivos `.puml` originales de `diagramas/02-casos-de-uso/`.
- Consultá los escenarios correspondientes de `diagramas/03-escenarios-casos-de-uso/`.
- Comparalos con los nuevos diagramas `.puml` del PR #190.
- Revisá también `diagramas_de_actividades.md`, `ia/a3/esp-actividades-3-4-5.md` y `changelog.md`.

**Requisitos de la consigna:**
- Cada diagrama debe representar al menos 10 actividades.
- Cada diagrama debe incluir al menos 3 carriles (swimlanes).
- Debe representar correctamente las decisiones, bifurcaciones y caminos alternativos que correspondan.
- Las actividades, responsabilidades y transiciones deben ser coherentes con los casos de uso y escenarios originales.
- Los archivos `.png` deben corresponder a sus fuentes PlantUML.
- La documentación de IA debe registrar prompts, contexto utilizado, ajustes e iteraciones.

**Tareas:**
1. Verificá los requisitos de cada uno de los cuatro diagramas por separado.
2. Detectá errores de lógica, condiciones faltantes, caminos alternativos omitidos y responsabilidades incorrectamente asignadas.
3. Identificá diferencias concretas con los casos de uso y escenarios originales, citando los archivos involucrados.
4. Verificá el índice, el changelog y la documentación de IA.
5. Clasificá los hallazgos como críticos, importantes o menores.
6. Proponé comentarios concretos, respetuosos y accionables para publicar en GitHub.

No inventes incumplimientos. Diferenciá los errores confirmados de las recomendaciones opcionales. Si no podés verificar algo, indicá expresamente qué falta para comprobarlo.

Presentá un informe estructurado y una conclusión sobre si el PR está listo para aprobarse o requiere correcciones.
```

### Output obtenido

# Revisión técnica del PR #190

**Alcance y método:** revisión de solo lectura del PR contra `develop`. Consulté los cuatro casos de uso originales `.puml`, los ocho escenarios asociados, los cuatro nuevos `.puml`, las imágenes `.png`, el índice, el changelog y el registro de IA. No modifiqué archivos ni publiqué comentarios, aprobé o integré el PR.

## Requisitos por diagrama

| Diagrama | Actividades | Carriles | Resultado |
|---|---:|---:|---|
| Preparar pedido | 22 | 3 roles distintos | Cumple los mínimos numéricos. Hay inconsistencias de flujo y responsabilidades que detallo abajo. |
| Cobrar cuenta | 22 | 4 | Cumple los mínimos numéricos. La decisión de autorización está ubicada antes de la validación del medio de pago. |
| Entregar pedido | 18 | 4 particiones | Cumple los mínimos numéricos. El registro de entrega aparece antes de la entrega física y falta una extensión del caso de uso. |
| Cancelar pedido | 17 | 4 | Cumple los mínimos numéricos. Falta la confirmación explícita posterior a validar el estado y no se condiciona claramente el aviso a cocina. |

El conteo corresponde a las acciones escritas en cada fuente PlantUML; no conté decisiones ni nodos iniciales/finales como actividades.

## Hallazgos importantes

### 1. Cobrar cuenta: la decisión ocurre antes de recibir el resultado del medio de pago

En el diagrama, el sistema solicita autorización y enseguida decide «¿Pago autorizado?». La validación y la devolución del resultado por el medio de pago aparecen **después** de esa bifurcación. Por lo tanto, el flujo no representa que la decisión dependa del resultado de la validación; además, la rama de reintento no vuelve a procesar el pago de manera coherente.

Esto difiere del escenario de rechazo, donde el medio rechaza la operación antes de que el sistema informe el resultado y ofrezca reintentar o cancelar. También deja desordenado el camino aprobado: el sistema registra el pago y genera el comprobante antes de que el carril del medio valide la operación.

- Fuentes: [diagrama de actividades de cobro](https://github.com/lucasmengarelli3/SistemaPedidos/blob/feature/esp-actividades-3-4-5-add-diagrama-actividad-3/diagramas/04-diagramas-actividades/04-actividad-cobrar-cuenta-04.puml), [caso de uso Cobrar cuenta](https://github.com/lucasmengarelli3/SistemaPedidos/blob/develop/diagramas/02-casos-de-uso/02-cobrar-cuenta.puml), [escenario de cobro aprobado](https://github.com/lucasmengarelli3/SistemaPedidos/blob/develop/diagramas/03-escenarios-casos-de-uso/03-cobrar-cuenta-flujo-principal-cobro-aprobado-07.md) y [escenario de pago rechazado](https://github.com/lucasmengarelli3/SistemaPedidos/blob/develop/diagramas/03-escenarios-casos-de-uso/03-cobrar-cuenta-flujo-alternativo-pago-rechazado-08.md).

**Comentario propuesto:**  
> ¿Podrían mover la validación del medio de pago y la devolución del resultado antes de la decisión «¿Pago autorizado?»? Así, el registro del pago y el comprobante quedan solo en la rama aprobada, y la rama rechazada puede reintentar desde una nueva autorización con otro medio.

### 2. Preparar pedido: inicio y selección asignados a mostrador, y sin decisión ante un estado inválido

El escenario dice que Cocina recibe la notificación automática, consulta la cola y selecciona el pedido. El diagrama asigna la consulta y la selección al usuario de mostrador, que además «envía la notificación de pedido recibido». Esto cambia quién inicia la preparación respecto del escenario.

Además, el diagrama incluye «Valida que el estado sea recibido» pero no una decisión ni una alternativa cuando no lo es, aunque el caso de uso define la transición `recibido → en preparación → listo`. El caso de uso también contempla «Reportar falta de insumos» como extensión; el diagrama no la muestra. El escenario deja ese último comportamiento como una pregunta, así que no hay base para inventar qué acciones siguen, pero sí conviene reflejar o aclarar esa extensión.

- Fuentes: [diagrama de actividades de preparación](https://github.com/lucasmengarelli3/SistemaPedidos/blob/feature/esp-actividades-3-4-5-add-diagrama-actividad-3/diagramas/04-diagramas-actividades/04-actividad-preparar-pedido-03.puml), [caso de uso Preparar pedido](https://github.com/lucasmengarelli3/SistemaPedidos/blob/develop/diagramas/02-casos-de-uso/02-preparar-pedido.puml), [escenario principal de preparación](https://github.com/lucasmengarelli3/SistemaPedidos/blob/develop/diagramas/03-escenarios-casos-de-uso/03-preparar-pedido-flujo-principal-pedido-listo-05.md) y [escenario de pedido inexistente](https://github.com/lucasmengarelli3/SistemaPedidos/blob/develop/diagramas/03-escenarios-casos-de-uso/03-preparar-pedido-flujo-excepcion-pedido-inexistente-06.md).

**Comentario propuesto:**  
> ¿Podrían alinear el inicio con el escenario —Cocina recibe la notificación, consulta la cola y selecciona el pedido— y agregar una rama cuando el estado no sea `recibido`? El caso de uso también define la extensión «Reportar falta de insumos»; como el escenario deja su resolución abierta, sugiero representarla como extensión pendiente de definición o aclarar su alcance.

### 3. Entregar pedido: orden del registro y extensión de cobro previo

La fuente registra la entrega en el historial antes de que el pedido se entregue físicamente y el cliente confirme. El escenario, en cambio, pone primero la entrega y confirmación del usuario y luego el cambio a `entregado` con registro de fecha y responsable. Además, el caso de uso original incluye «Verificar cobro previo del pedido» como extensión y el diagrama no la refleja. Los escenarios no detallan esa extensión, así que no se puede inferir aquí si es una condición obligatoria para toda entrega.

- Fuentes: [diagrama de actividades de entrega](https://github.com/lucasmengarelli3/SistemaPedidos/blob/feature/esp-actividades-3-4-5-add-diagrama-actividad-3/diagramas/04-diagramas-actividades/04-actividad-entregar-pedido-05.puml), [caso de uso Entregar pedido](https://github.com/lucasmengarelli3/SistemaPedidos/blob/develop/diagramas/02-casos-de-uso/02-entregar-pedido.puml), [escenario principal de entrega](https://github.com/lucasmengarelli3/SistemaPedidos/blob/develop/diagramas/03-escenarios-casos-de-uso/03-entregar-pedido-flujo-principal-entrega-validada-09.md) y [escenario de datos no coincidentes](https://github.com/lucasmengarelli3/SistemaPedidos/blob/develop/diagramas/03-escenarios-casos-de-uso/03-entregar-pedido-flujo-alternativo-datos-no-coinciden-10.md).

**Comentario propuesto:**  
> ¿Podrían mover el registro de la entrega en el historial para después de la entrega y confirmación del usuario? El escenario define que el sistema actualiza el estado y registra fecha/responsable una vez confirmada. También falta reflejar la extensión «Verificar cobro previo» del caso de uso o aclarar por qué no aplica en este flujo.

### 4. Cancelar pedido: falta confirmación explícita y la notificación a Cocina no está condicionada por una rama

El escenario principal indica que el usuario confirma la operación después de que el sistema valida el estado. El diagrama solicita confirmación antes de la validación y luego no muestra una acción explícita que la registre. También el escenario especifica que se notifica a Cocina **si** el pedido estaba en preparación. El diagrama pasa por el carril de Cocina tanto si el pedido estaba recibido como si estaba en preparación; «si correspondía» aparece solo como texto de una actividad, no como condición de flujo.

- Fuentes: [diagrama de actividades de cancelación](https://github.com/lucasmengarelli3/SistemaPedidos/blob/feature/esp-actividades-3-4-5-add-diagrama-actividad-3/diagramas/04-diagramas-actividades/04-actividad-cancelar-pedido-06.puml), [caso de uso Cancelar pedido](https://github.com/lucasmengarelli3/SistemaPedidos/blob/develop/diagramas/02-casos-de-uso/02-cancelar-pedido.puml), [escenario de cancelación autorizada](https://github.com/lucasmengarelli3/SistemaPedidos/blob/develop/diagramas/03-escenarios-casos-de-uso/03-cancelar-pedido-flujo-principal-cancelacion-autorizada-11.md) y [escenario de estado no cancelable](https://github.com/lucasmengarelli3/SistemaPedidos/blob/develop/diagramas/03-escenarios-casos-de-uso/03-cancelar-pedido-flujo-excepcion-estado-no-cancelable-12.md).

**Comentario propuesto:**  
> ¿Podrían agregar la confirmación explícita del usuario después de validar que el pedido es cancelable y antes de cambiar su estado? También convendría modelar una decisión para notificar a Cocina solo cuando el pedido estaba `en preparación`, como indica el escenario.

### 5. Las imágenes muestran caracteres acentuados mal codificados

En las cuatro imágenes consultadas se ven cadenas como «cancelaciÃ³n», «preparaciÃ³n» y «notificaciÃ³n», mientras que las fuentes `.puml` contienen los términos acentuados correctamente. La estructura de los diagramas corresponde a sus fuentes, pero las etiquetas no se representan fielmente en las imágenes.

**Comentario propuesto:**  
> ¿Podrían regenerar los cuatro PNG con la codificación de caracteres corregida? En las imágenes los acentos aparecen como `Ã³`/`Ã³n` (por ejemplo, «cancelaciÃ³n»), aunque las fuentes PlantUML tienen el texto correcto.

## Hallazgos menores y documentación

- **Índice:** el archivo [diagramas_de_actividades.md](https://github.com/lucasmengarelli3/SistemaPedidos/blob/feature/esp-actividades-3-4-5-add-diagrama-actividad-3/diagramas/04-diagramas-actividades/diagramas_de_actividades.md) enlaza los cuatro PNG y sus fuentes PlantUML con rutas relativas correctas. No encontré problemas en esos enlaces.
- **Changelog:** [changelog.md](https://github.com/lucasmengarelli3/SistemaPedidos/blob/feature/esp-actividades-3-4-5-add-diagrama-actividad-3/changelog.md) registra la entrega, los casos 3–6 y los enlaces a issues y PR. No detecté un incumplimiento concreto.
- **Registro de IA:** [esp-actividades-3-4-5.md](https://github.com/lucasmengarelli3/SistemaPedidos/blob/feature/esp-actividades-3-4-5-add-diagrama-actividad-3/ia/a3/esp-actividades-3-4-5.md) incluye el prompt, una lista de contexto que cubre los cuatro casos y escenarios, y una sección de ajustes. Sin embargo, el título dice «Casos de uso 3, 4 y 5», aunque el contenido trata también el caso 6; el prompt también contiene nombres de archivos incorrectos para cobro y cancelación. La sección de ajustes no documenta iteraciones concretas ni deja constancia de si no hubo iteraciones. **Menor, confirmado:** convendría corregir esos datos y registrar las iteraciones realizadas, o indicar expresamente que no hubo.
  
## Clasificación y conclusión

**Importantes:** orden de autorización y validación en cobro; inicio y manejo de estado en preparación; orden del registro y extensión omitida en entrega; confirmación y condición de notificación en cancelación; codificación defectuosa visible en los PNG. **Menores:** inconsistencias y falta de trazabilidad de iteraciones en el registro de IA. **Críticos:** no encontré hallazgos de esa severidad.

**Conclusión: el PR requiere correcciones antes de aprobarse.** Las fuentes contienen discrepancias confirmadas con los casos de uso y escenarios, además de las etiquetas dañadas en las imágenes. Las observaciones sobre extensiones cuyo comportamiento no detallan los escenarios están señaladas como tales; no asumí reglas de negocio adicionales.

### Evaluación y ajustes humanos

Las observaciones de Copilot se revisaron antes de publicarlas en GitHub.

**Hallazgos aceptados:**

- Se comprobó directamente en el código de `prepararPedido` que algunas actividades estaban asignadas a un carril diferente del indicado en el escenario original.
- Se confirmó que la validación del estado no tenía un camino alternativo.
- Se aceptaron las observaciones sobre el orden de autorización del cobro y el registro de la entrega.
- Se comprobó en el código de `cancelarPedido` que la confirmación estaba ubicada antes de la validación y que la notificación a Cocina no tenía una condición específica.
- Se abrieron las imágenes y se confirmó visualmente el problema de los caracteres acentuados.

**Ajustes realizados a las sugerencias de IA:**

- Se reformularon los comentarios propuestos por Copilot para que fueran más breves, claros y fáciles de entender.
- Las flechas largas se consideraron una sugerencia de presentación, no un error funcional confirmado.
- No se exigieron flujos nuevos para las extensiones «Reportar falta de insumos» y «Verificar cobro previo», porque los escenarios no explicaban suficientemente su comportamiento.
- Las aclaraciones sobre el registro de IA se incluyeron como observación general, sin tratarlas como errores graves.

La decisión de solicitar correcciones fue tomada después de evaluar los hallazgos y no automáticamente por la recomendación de Copilot.

### Revisión publicada en GitHub

- **Enlace a la revisión:** [PR #190 — Conversación y revisiones](https://github.com/lucasmengarelli3/SistemaPedidos/pull/190)
- **Decisión:** Request changes (solicitar cambios).
- **Correcciones solicitadas:** seis comentarios sobre los flujos de preparación, cobro, entrega y cancelación. También se solicitaron correcciones de codificación en los PNG y aclaraciones en la documentación de IA.
- **Resultado final:** Pendiente. Se espera que el autor aplique las correcciones y resuelva el conflicto de integración detectado en `changelog.md` antes de una nueva revisión.

---

## Revisión 2

**PR:** [#193 — Diagramas de actividades CU1 y CU2](https://github.com/lucasmengarelli3/SistemaPedidos/pull/193)  
**Autor:** @tomx2002-droid  
**Rol revisado:** Especialista en Diagramas de Actividades — Casos de uso 1 y 2  
**Fecha:** 21/10/2026  
**Estado:** Revisión publicada. Correcciones solicitadas, pendientes de verificar.

### Archivos de contexto

Se utilizaron los archivos del PR #193 y los artefactos originales de A2.

**Casos de uso:**
- `diagramas/02-casos-de-uso/02-registrar-pedido.puml`
- `diagramas/02-casos-de-uso/02-modificar-pedido.puml`

**Escenarios:**
- `diagramas/03-escenarios-casos-de-uso/03-registrar-pedido-flujo-principal-registro-exitoso-01.md`
- `diagramas/03-escenarios-casos-de-uso/03-registrar-pedido-flujo-alternativo-producto-no-disponible-02.md`
- `diagramas/03-escenarios-casos-de-uso/03-modificar-pedido-flujo-principal-modificacion-recibida-03.md`
- `diagramas/03-escenarios-casos-de-uso/03-modificar-pedido-flujo-excepcion-pedido-no-modificable-04.md`

**Archivos revisados del PR:**
- `diagramas/04-diagramas-actividades/04-actividad-registrar-pedido-01.puml`
- `diagramas/04-diagramas-actividades/04-actividad-registrar-pedido-01.png`
- `diagramas/04-diagramas-actividades/04-actividad-modificar-pedido-02.puml`
- `diagramas/04-diagramas-actividades/04-actividad-modificar-pedido-02.png`
- `diagramas/04-diagramas-actividades/diagramas_de_actividades.md`
- `ia/a3/esp-actividades-1-2.md`

También se verificó que `changelog.md` no fue modificado en el PR.

### Prompt utilizado

Se utilizó GitHub Copilot Chat en modo Agent. Primero se verificó el acceso a los archivos del PR y a los escenarios originales de A2. Luego se envió el siguiente prompt para la revisión técnica:

```text
Actuá como revisor técnico del Pull Request #193 del repositorio `lucasmengarelli3/SistemaPedidos`, que incorpora diagramas de actividades para los casos de uso Registrar Pedido (CU1) y Modificar Pedido (CU2).

Realizá una revisión técnica de solo lectura. No modifiques archivos, no ejecutes comandos que alteren el repositorio, no publiques comentarios, no apruebes ni hagas merge.

**Contexto obligatorio:**
- Consultá `diagramas/02-casos-de-uso/02-registrar-pedido.puml` y `02-modificar-pedido.puml` en `develop`.
- Consultá los cuatro escenarios correspondientes en `diagramas/03-escenarios-casos-de-uso/`: registro exitoso, producto no disponible, modificación recibida y pedido no modificable.
- Comparalos con los dos nuevos archivos `.puml` del PR #193.
- Revisá los dos `.png`, `diagramas_de_actividades.md`, `ia/a3/esp-actividades-1-2.md` y verificá si el PR actualiza `changelog.md`.

**Requisitos de la consigna:**
- Cada diagrama debe contener al menos 10 actividades y 3 carriles (swimlanes).
- Debe representar decisiones, bifurcaciones y caminos alternativos cuando correspondan.
- Los actores, las responsabilidades y el orden de las acciones deben coincidir con los casos de uso y escenarios originales.
- Las imágenes `.png` deben representar correctamente sus fuentes PlantUML.
- El índice debe permitir acceder a los diagramas.
- El registro de IA debe incluir el prompt utilizado, los archivos de contexto, los ajustes realizados y las iteraciones relevantes.
- El changelog debe registrar las contribuciones del PR.

**Tareas:**
1. Verificá los requisitos mínimos de CU1 y CU2 por separado.
2. Analizá especialmente qué ocurre en CU1 cuando los datos no son válidos: comprobá si el flujo continúa hacia Cocina sin generar ni guardar el pedido.
3. Analizá especialmente qué ocurre en CU2 cuando las reglas de negocio no son válidas: comprobá si el usuario puede corregir y revalidar los cambios o si el flujo termina sin registrar la modificación.
4. Identificá otras inconsistencias concretas con los casos de uso y escenarios originales, incluyendo el escenario de producto no disponible.
5. Verificá el índice, los PNG, el registro de IA y el changelog.
6. Clasificá los hallazgos como críticos, importantes o menores.
7. Proponé comentarios respetuosos, claros y accionables para publicar en GitHub.

No inventes incumplimientos. Diferenciá los errores confirmados de las mejoras opcionales. Si algo no puede verificarse, indicá qué falta para comprobarlo.

Presentá un informe estructurado, citando los archivos involucrados, y concluí si el PR está listo para aprobarse o requiere correcciones.
```

### Output obtenido

# Revisión técnica del PR #193

**Alcance:** revisión de solo lectura del PR #193, rama `feature/esp-actividades-1-2-add-diagramas` contra `develop`. Consulté los dos casos de uso originales, los cuatro escenarios de A2, las dos fuentes PlantUML y sus PNG, el índice y el registro de IA. El PR modifica seis archivos y **no incluye `changelog.md`**. No modifiqué archivos, no publiqué comentarios ni aprobé o integré el PR.

## Requisitos mínimos

| Diagrama | Actividades | Carriles | Resultado |
|---|---:|---:|---|
| CU1 — Registrar pedido | 19 | 3 | Cumple los mínimos numéricos; el flujo alternativo de datos inválidos está mal conectado. |
| CU2 — Modificar pedido | 19 | 3 | Cumple los mínimos numéricos; el flujo de validación fallida termina sin completar ni revalidar los cambios. |

El conteo considera las acciones, no los nodos de inicio, fin o decisión.

## Hallazgos importantes

### 1. CU1: los datos inválidos no detienen ni reinician el flujo

En [04-actividad-registrar-pedido-01.puml](https://github.com/lucasmengarelli3/SistemaPedidos/blob/feature/esp-actividades-1-2-add-diagramas/diagramas/04-diagramas-actividades/04-actividad-registrar-pedido-01.puml), la rama «No» de «¿Datos válidos?» lleva a corregir los datos y recalcular el total; al terminar la decisión, el flujo continúa hacia Cocina, muestra una confirmación y entrega un número de pedido. No vuelve a validar los datos ni genera y guarda el pedido como `recibido`.

Es un error confirmado de flujo: se puede representar que un pedido inválido llega a Cocina sin pasar por la generación del identificador ni el guardado. El escenario de registro exitoso establece que esos pasos ocurren al registrar el pedido, y el escenario de producto no disponible exige bloquear la incorporación del producto y continuar con otra elección o descartar el borrador.

**Comentario propuesto:**
> ¿Podrían corregir la rama «No» de «¿Datos válidos?» para que, después de corregir los datos, vuelva a validar —o termine si se descarta el borrador—? Tal como está, ambas ramas continúan hacia Cocina y la confirmación, aunque la rama inválida no genera identificador ni guarda el pedido.

### 2. CU1: no se representa el escenario de producto no disponible

El escenario [03-registrar-pedido-flujo-alternativo-producto-no-disponible-02.md](https://github.com/lucasmengarelli3/SistemaPedidos/blob/develop/diagramas/03-escenarios-casos-de-uso/03-registrar-pedido-flujo-alternativo-producto-no-disponible-02.md) especifica que el sistema vuelve a consultar la disponibilidad, bloquea la incorporación del producto y permite elegir otro o abandonar el pedido. El diagrama no muestra esa validación ni sus caminos alternativos. La decisión genérica sobre datos válidos no modela explícitamente ese escenario.

**Comentario propuesto:**
> ¿Podrían agregar el flujo alternativo de producto no disponible: revalidar disponibilidad, impedir que se agregue el producto y permitir elegir otro o descartar el borrador? Ese escenario de A2 no queda representado actualmente.

### 3. CU2: una validación fallida no permite revalidar ni registrar la modificación

En [04-actividad-modificar-pedido-02.puml](https://github.com/lucasmengarelli3/SistemaPedidos/blob/feature/esp-actividades-1-2-add-diagramas/diagramas/04-diagramas-actividades/04-actividad-modificar-pedido-02.puml), si «¿Reglas de negocio válidas?» resulta «No», el usuario ajusta los cambios y el sistema recalcula el total; después el flujo termina. No vuelve a validar ni persiste el pedido, genera la comanda o confirma la modificación. Por lo tanto, la ruta de corrección no alcanza un resultado exitoso.

**Comentario propuesto:**
> ¿Podrían hacer que, después de «Ajustar cambios», el flujo vuelva a validar las reglas antes de continuar? Ahora la rama inválida recalcula el total y termina sin persistir ni confirmar; así, el usuario no puede completar la corrección.

### 4. CU2: la confirmación del usuario está antes de la validación y el recálculo

El escenario principal [03-modificar-pedido-flujo-principal-modificacion-recibida-03.md](https://github.com/lucasmengarelli3/SistemaPedidos/blob/develop/diagramas/03-escenarios-casos-de-uso/03-modificar-pedido-flujo-principal-modificacion-recibida-03.md) indica que el sistema valida las reglas y recalcula el total; luego el usuario confirma con el resumen y el nuevo total. En el diagrama, «Confirmar cambios» ocurre antes de «Validar disponibilidad» y «Recalcular total». El orden no coincide y la confirmación no puede basarse en el total recalculado.

**Comentario propuesto:**
> ¿Podrían mover «Confirmar cambios» después de validar las reglas y recalcular el total? El escenario principal indica que el usuario confirma con el resumen y el nuevo total, que el diagrama calcula después de esa confirmación.

## Otras comprobaciones

- **Estado no modificable en CU2:** el diagrama comprueba si el estado es `recibido` y la rama «No» bloquea la edición, informa y termina. Esto concuerda con el escenario de excepción, que rechaza la operación y preserva el pedido.
- **PNG:** inspeccioné visualmente [04-actividad-registrar-pedido-01.png](https://github.com/lucasmengarelli3/SistemaPedidos/blob/feature/esp-actividades-1-2-add-diagramas/diagramas/04-diagramas-actividades/04-actividad-registrar-pedido-01.png) y [04-actividad-modificar-pedido-02.png](https://github.com/lucasmengarelli3/SistemaPedidos/blob/feature/esp-actividades-1-2-add-diagramas/diagramas/04-diagramas-actividades/04-actividad-modificar-pedido-02.png). Sus decisiones y actividades corresponden a las fuentes `.puml` consultadas; los errores de flujo señalados también se ven en las imágenes. No regeneré los PNG para hacer una comparación byte a byte.
- **Índice:** [diagramas_de_actividades.md](https://github.com/lucasmengarelli3/SistemaPedidos/blob/feature/esp-actividades-1-2-add-diagramas/diagramas/04-diagramas-actividades/diagramas_de_actividades.md) enlaza ambos `.puml` con rutas relativas válidas. **Mejora opcional:** incluir enlaces a los `.png` para acceder directamente a la representación visual.
- **Documentación de IA:** [esp-actividades-1-2.md](https://github.com/lucasmengarelli3/SistemaPedidos/blob/feature/esp-actividades-1-2-add-diagramas/ia/a3/esp-actividades-1-2.md) registra el prompt, los archivos de contexto y ajustes realizados. No detalla iteraciones concretas. Con el documento disponible no puedo determinar si no hubo iteraciones o si faltó registrarlas; convendría aclararlo.
- **Changelog:** `changelog.md` no forma parte de los seis archivos modificados del PR. **Importante, confirmado:** el PR no registra sus contribuciones en el changelog.

## Clasificación y conclusión

**Importantes:** flujo inválido de CU1 continúa como si el pedido se hubiera registrado; ausencia del alternativo de producto no disponible; corrección fallida de CU2 termina sin revalidación ni persistencia; orden incorrecto de validación/total y confirmación en CU2; ausencia de actualización del changelog. **Críticos:** no encontré hallazgos de esa categoría. **Menores:** el índice no enlaza directamente a los PNG; las iteraciones de IA no quedan verificables en el registro.

**Conclusión: el PR requiere correcciones antes de aprobarse.** Los dos diagramas cumplen los mínimos de actividades y carriles, pero contienen errores confirmados en caminos que impiden o simulan completar los flujos, y CU1 no representa el escenario alternativo de producto no disponible.

### Evaluación y ajustes humanos

Las observaciones de Copilot se analizaron antes de publicar la revisión en GitHub, contrastándolas con los diagramas y escenarios originales de A2.

**Hallazgos aceptados:**

- En CU1 se confirmó que la rama de datos inválidos continúa hacia Cocina sin volver a validar ni completar el registro del pedido.
- Se aceptó la observación sobre la ausencia del escenario alternativo de producto no disponible.
- En CU2 se confirmó que la rama de validación fallida termina sin permitir completar la corrección.
- Se aceptó la observación sobre el orden incorrecto entre la confirmación del usuario, la validación y el recálculo del total.
- Se verificó que `changelog.md` no estaba incluido entre los archivos modificados del PR.

**Ajustes realizados a las sugerencias de IA:**

- Se reformularon los cuatro comentarios técnicos para que fueran más breves, claros y específicos.
- No se exigió agregar enlaces a los PNG en el índice, porque los enlaces existentes a los archivos `.puml` eran válidos y cumplían la función requerida.
- Se revisó directamente el contenido de `ia/a3/esp-actividades-1-2.md` antes de comentar. Se solicitó incluir el output concreto, aclarar si hubo iteraciones y corregir las rutas de los escenarios de A2.
- La ausencia de actualización del changelog se reservó para el comentario general, porque ese archivo no formaba parte del diff.

La decisión de solicitar correcciones fue tomada después de evaluar los hallazgos, no automáticamente por la recomendación de Copilot.

### Revisión publicada en GitHub

- **Enlace a la revisión:** [PR #193 — Conversación y revisiones](https://github.com/lucasmengarelli3/SistemaPedidos/pull/193)
- **Decisión:** Request changes (solicitar cambios).
- **Correcciones solicitadas:** cuatro comentarios técnicos sobre los flujos de Registrar Pedido y Modificar Pedido, y un comentario sobre la documentación de IA. En el comentario general se solicitó actualizar `changelog.md`.
- **Resultado final:** Pendiente. Se espera que el autor aplique las correcciones para realizar una nueva revisión.

---

## Revisión 3

**PR:** Pendiente
**Autor:** Pendiente
**Rol revisado:** Pendiente
**Fecha:** Pendiente
**Estado:** Pendiente

### Archivos de contexto

### Prompt utilizado

```text
[PROMPT REAL UTILIZADO]
```

### Output obtenido

### Evaluación y ajustes humanos

### Revisión publicada en GitHub

- **Enlace a la revisión:** Pendiente
- **Decisión:** Pendiente
- **Correcciones solicitadas:** Pendiente
- **Resultado final:** Pendiente

---

## Revisión 4

**PR:** Pendiente
**Autor:** Pendiente
**Rol revisado:** Pendiente
**Fecha:** Pendiente
**Estado:** Pendiente

### Archivos de contexto

### Prompt utilizado

```text
[PROMPT REAL UTILIZADO]
```

### Output obtenido

### Evaluación y ajustes humanos

### Revisión publicada en GitHub

- **Enlace a la revisión:** Pendiente
- **Decisión:** Pendiente
- **Correcciones solicitadas:** Pendiente
- **Resultado final:** Pendiente

---

## Resumen de revisiones

| Revisión | PR | Rol revisado | Hallazgos validados | Decisión humana | Enlace |
| --- | --- | --- | --- | --- | --- |
| 1 | #190 | Especialista en Diagramas de Actividades (CU 3–6) | Flujos de preparación, cobro, entrega y cancelación; codificación de PNG; registro de IA | Request changes | [PR #190](https://github.com/lucasmengarelli3/SistemaPedidos/pull/190) |
| 2 | #193 | Especialista en Diagramas de Actividades (CU 1–2) | Validaciones y caminos alternativos de CU1 y CU2; orden de confirmación; changelog y registro de IA | Request changes | [PR #193](https://github.com/lucasmengarelli3/SistemaPedidos/pull/193) |
| 3 | Pendiente | Pendiente | Pendiente | Pendiente | Pendiente |
| 4 | Pendiente | Pendiente | Pendiente | Pendiente | Pendiente |

## Conclusiones

<!-- Al finalizar las cuatro revisiones, explicar cómo se utilizó la IA, qué aportó al control de calidad, qué errores o sugerencias se descartaron y qué decisiones se tomaron mediante revisión humana. -->