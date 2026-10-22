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

**PR:** [#193](https://github.com/lucasmengarelli3/SistemaPedidos/pull/193) — segunda revisión sobre nuevos commits
**Autor:** @tomx2002-droid
**Rol revisado:** Especialista en Diagramas de Actividades (CU 1 y 2)
**Fecha:** 21/10/2026
**Estado:** Request changes publicado — correcciones pendientes

### Archivos de contexto

- `diagramas/04-diagramas-actividades/04-actividad-registrar-pedido-01.puml`
- `diagramas/04-diagramas-actividades/04-actividad-modificar-pedido-02.puml`
- PNG correspondientes a ambos diagramas.
- `ia/a3/esp-actividades-1-2.md`
- `changelog.md`
- Casos de uso y escenarios originales de A2.
- Comparación de commits: `ec2f36f` → `51a8cbb`.

### Prompt utilizado

```text
Actuá como revisor técnico de UML y documentación de un proyecto académico.

Necesito realizar una **segunda revisión asistida por IA del Pull Request #193**, correspondiente a los diagramas de actividades de los Casos de Uso 1 (Registrar pedido) y 2 (Modificar pedido).

Repositorio: `lucasmengarelli3/SistemaPedidos`

Rama del PR: `feature/esp-actividades-1-2-add-diagramas`

Commits a comparar:

- Versión revisada anteriormente: `ec2f36f`
- Versión corregida: `51a8cbb`
**Objetivo:** verificar si los cambios posteriores a mi primera revisión resolvieron los hallazgos y si introdujeron problemas nuevos.

### Archivos a revisar

- `diagramas/04-diagramas-actividades/04-actividad-registrar-pedido-01.puml`
- `diagramas/04-diagramas-actividades/04-actividad-modificar-pedido-02.puml`
- Los PNG correspondientes a ambos diagramas.
- `ia/a3/esp-actividades-1-2.md`
- `changelog.md`
- Los casos de uso y escenarios originales de A2 que correspondan.
Utilizá los archivos reales del repositorio y verificá las rutas antes de citar documentación.

### Hallazgos de la primera revisión

1. **CU1:** cuando los datos eran inválidos, el flujo podía continuar sin generar identificador ni persistir el pedido.
2. **CU1:** faltaba contemplar el producto no disponible.
3. **CU2:** cuando las reglas de negocio eran inválidas, el flujo terminaba después de ajustar cambios, sin revalidar.
4. **CU2:** el usuario confirmaba los cambios antes de que el sistema validara y recalculara el total.
5. **Documentación de IA:** faltaban detalles del output, las iteraciones y la verificación de las rutas de contexto.
6. **Changelog:** faltaba registrar la contribución del autor.

### Instrucciones

1. Compará las versiones `ec2f36f` y `51a8cbb`, centrándote en los archivos del PR y no en cambios heredados de `develop`.
2. Para cada hallazgo anterior, indicá si está **resuelto, parcialmente resuelto o pendiente**, explicando por qué.
3. Analizá la lógica de los bucles `repeat` y las decisiones de ambos diagramas. Verificá especialmente qué sucede cuando se corrigen datos inválidos o se selecciona otro producto.
4. Comprobá la coherencia con los escenarios originales de A2.
5. Revisá la documentación de IA: prompt, archivos de contexto, output, iteraciones y ajustes humanos. No supongas que una respuesta resumida equivale al código originalmente generado.
6. Revisá si la nueva entrada de `changelog.md` respeta la estructura de `Unreleased`.
7. Comprobá que los PNG reflejen los `.puml` actualizados, si disponés de medios para inspeccionarlos.
8. Identificá posibles regresiones o inconsistencias nuevas.
9. No modifiques archivos, no hagas commits, no publiques comentarios ni apruebes el PR.

### Formato de respuesta
**A. Tabla de hallazgos anteriores:** hallazgo, estado, evidencia concreta (archivo y línea) y justificación.

**B. Problemas nuevos:** archivo, línea, severidad y explicación.

**C. Documentación y changelog:** pendientes concretos, si existen.

**D. Verificaciones no realizadas:** indicá expresamente lo que no pudiste comprobar.

**E. Propuesta de comentario para GitHub:** redactá un comentario breve, claro y constructivo, limitado a los problemas comprobados. Diferenciá los bloqueantes de las sugerencias.

No inventes evidencia. Si no podés acceder a una rama, commit, archivo o imagen, indicámelo en lugar de asumir que lo revisaste.
```

### Output obtenido

**Revisión comparativa:** `ec2f36f` → `51a8cbb57f346881a169996ecaa99a7bf29241e6` en el PR #193. Consulté las fuentes actualizadas, los PNG, la documentación, el changelog y los casos de uso y escenarios correspondientes de A2 en `develop`. La comparación se centra en los archivos del PR, no en cambios heredados de `develop`.

## A. Estado de los hallazgos anteriores

| Hallazgo | Estado | Evidencia y justificación |
|---|---|---|
| **CU1: los datos inválidos podían continuar sin validar, generar identificador ni guardar el pedido.** | **Resuelto** | En [04-actividad-registrar-pedido-01.puml, líneas 37–46](https://github.com/lucasmengarelli3/SistemaPedidos/blob/51a8cbb57f346881a169996ecaa99a7bf29241e6/diagramas/04-diagramas-actividades/04-actividad-registrar-pedido-01.puml#L37-L46), corregir los datos conduce a una nueva validación. El bucle sale por la rama de datos válidos y luego sigue hacia confirmación y persistencia, líneas [48–55](https://github.com/lucasmengarelli3/SistemaPedidos/blob/51a8cbb57f346881a169996ecaa99a7bf29241e6/diagramas/04-diagramas-actividades/04-actividad-registrar-pedido-01.puml#L48-L55). |
| **CU1: faltaba el camino alternativo de producto no disponible.** | **Parcialmente resuelto** | Ahora existe la decisión «¿Producto disponible?» y la acción «Elegir otro producto o descartar», líneas [22–30](https://github.com/lucasmengarelli3/SistemaPedidos/blob/51a8cbb57f346881a169996ecaa99a7bf29241e6/diagramas/04-diagramas-actividades/04-actividad-registrar-pedido-01.puml#L22-L30). Sin embargo, ambos resultados siguen a personalizaciones, referencia, validación y eventual registro. No se representa volver a agregar/revalidar el producto elegido ni terminar si se descarta. |
| **CU2: tras reglas inválidas se ajustaba, pero no se revalidaba.** | **Resuelto** | El bucle de las líneas [30–39](https://github.com/lucasmengarelli3/SistemaPedidos/blob/51a8cbb57f346881a169996ecaa99a7bf29241e6/diagramas/04-diagramas-actividades/04-actividad-modificar-pedido-02.puml#L30-L39) retorna a validar cuando las reglas siguen siendo inválidas y sale cuando son válidas. |
| **CU2: se confirmaba antes de validar y recalcular el total.** | **Resuelto** | El sistema recalcula y muestra el total antes de que el usuario confirme; luego persiste los cambios. Ver líneas [41–50](https://github.com/lucasmengarelli3/SistemaPedidos/blob/51a8cbb57f346881a169996ecaa99a7bf29241e6/diagramas/04-diagramas-actividades/04-actividad-modificar-pedido-02.puml#L41-L50). |
| **Documentación de IA incompleta.** | **Parcialmente resuelto** | Ahora registra prompt, resumen de output, iteraciones y ajustes, líneas [3–5](https://github.com/lucasmengarelli3/SistemaPedidos/blob/51a8cbb57f346881a169996ecaa99a7bf29241e6/ia/a3/esp-actividades-1-2.md#L3-L5) y [20–44](https://github.com/lucasmengarelli3/SistemaPedidos/blob/51a8cbb57f346881a169996ecaa99a7bf29241e6/ia/a3/esp-actividades-1-2.md#L20-L44). Pero los nombres de los escenarios citados no corresponden a las rutas reales de A2, y no incluye el código PlantUML que la IA habría producido originalmente; por eso no se pueden cotejar las afirmaciones sobre iteraciones con ese output. |
| **Faltaba registrar la contribución en el changelog.** | **Resuelto** | La entrada actual identifica rama, contribución, issues, PR y autora/rol: [changelog.md, líneas 9–13](https://github.com/lucasmengarelli3/SistemaPedidos/blob/51a8cbb57f346881a169996ecaa99a7bf29241e6/changelog.md#L9-L13). |

## B. Problemas nuevos o aún presentes

| Archivo | Línea(s) | Severidad | Problema comprobado |
|---|---:|---|---|
| [04-actividad-registrar-pedido-01.puml](https://github.com/lucasmengarelli3/SistemaPedidos/blob/51a8cbb57f346881a169996ecaa99a7bf29241e6/diagramas/04-diagramas-actividades/04-actividad-registrar-pedido-01.puml) | 22–34, 52–55 | **Importante** | La rama de producto no disponible no distingue «elegir otro» de «descartar». En ambos casos actualiza la selección y sigue al resto del alta; por tanto, elegir otro no vuelve a agregar ni a comprobar disponibilidad, y descartar puede seguir hasta crear y guardar el pedido. Esto no satisface el escenario de A2, que requiere reintentar desde la selección o descartar el borrador. |
| [04-actividad-registrar-pedido-01.puml](https://github.com/lucasmengarelli3/SistemaPedidos/blob/51a8cbb57f346881a169996ecaa99a7bf29241e6/diagramas/04-diagramas-actividades/04-actividad-registrar-pedido-01.puml) | 48–54 | **Importante** | El usuario confirma antes de que el sistema calcule el total final. El escenario principal de A2 ordena validar y calcular el total antes de confirmar; el diagrama solo calcula precios vigentes al inicio y calcula el total del pedido después de la confirmación. |
| [04-actividad-modificar-pedido-02.puml](https://github.com/lucasmengarelli3/SistemaPedidos/blob/51a8cbb57f346881a169996ecaa99a7bf29241e6/diagramas/04-diagramas-actividades/04-actividad-modificar-pedido-02.puml) | 16–17, 49–50 | **Importante** | El estado solo se verifica antes de iniciar la edición. El caso de uso de A2 también prevé rechazar la modificación si el pedido cambia de estado durante la edición; no hay una segunda verificación antes de persistir. En una edición concurrente, el flujo podría guardar cambios pese a que el pedido ya no esté en `recibido`. |

**Coherencia con A2:** el orden del total en CU1 contradice [el escenario de registro exitoso](https://github.com/lucasmengarelli3/SistemaPedidos/blob/develop/diagramas/03-escenarios-casos-de-uso/03-registrar-pedido-flujo-principal-registro-exitoso-01.md#L16-L24). El camino alternativo incompleto contradice [el escenario de producto no disponible](https://github.com/lucasmengarelli3/SistemaPedidos/blob/develop/diagramas/03-escenarios-casos-de-uso/03-registrar-pedido-flujo-alternativo-producto-no-disponible-02.md#L16-L24). La ausencia de revalidación del estado en CU2 difiere del punto de extensión documentado en [el caso de uso Modificar pedido](https://github.com/lucasmengarelli3/SistemaPedidos/blob/develop/diagramas/02-casos-de-uso/02-modificar-pedido.puml#L27-L35). La revalidación de los datos en CU1 y de las reglas en CU2 sí queda representada por sus bucles.

## C. Documentación y changelog

- **Rutas de contexto de IA:** el registro cita `03-registrar-pedido-flujo-principal.md` y `03-modificar-pedido-flujo-principal.md` ([líneas 11–17](https://github.com/lucasmengarelli3/SistemaPedidos/blob/51a8cbb57f346881a169996ecaa99a7bf29241e6/ia/a3/esp-actividades-1-2.md#L11-L17)). Las rutas reales consultadas son [03-registrar-pedido-flujo-principal-registro-exitoso-01.md](https://github.com/lucasmengarelli3/SistemaPedidos/blob/develop/diagramas/03-escenarios-casos-de-uso/03-registrar-pedido-flujo-principal-registro-exitoso-01.md) y [03-modificar-pedido-flujo-principal-modificacion-recibida-03.md](https://github.com/lucasmengarelli3/SistemaPedidos/blob/develop/diagramas/03-escenarios-casos-de-uso/03-modificar-pedido-flujo-principal-modificacion-recibida-03.md). Tampoco se enumeran los dos escenarios alternativos que se usan en la revisión: [producto no disponible](https://github.com/lucasmengarelli3/SistemaPedidos/blob/develop/diagramas/03-escenarios-casos-de-uso/03-registrar-pedido-flujo-alternativo-producto-no-disponible-02.md) y [pedido no modificable](https://github.com/lucasmengarelli3/SistemaPedidos/blob/develop/diagramas/03-escenarios-casos-de-uso/03-modificar-pedido-flujo-excepcion-pedido-no-modificable-04.md).
- **Output e iteraciones de IA:** existe una respuesta textual resumida y una descripción de tres iteraciones, pero no el output original de código. Por lo tanto, la documentación mejoró, pero no permite confirmar qué código produjo originalmente la IA ni cotejarlo con los ajustes humanos.
- **Índice:** [diagramas_de_actividades.md](https://github.com/lucasmengarelli3/SistemaPedidos/blob/51a8cbb57f346881a169996ecaa99a7bf29241e6/diagramas/04-diagramas-actividades/diagramas_de_actividades.md) enlaza las fuentes PlantUML. Es accesible; no incluye enlaces directos a los PNG, una mejora opcional.
- **Changelog:** registra la contribución y la atribuye a `@tomx2002-droid`. La estructura sigue el patrón existente del repositorio —`[Unreleased]`, encabezado fechado y sección `Added`—. Si se pretende que la entrada quede estrictamente dentro de `Unreleased`, el encabezado de release fechado no la expresa como no publicada; no lo considero un incumplimiento claro frente a la convención observada en el archivo.

## D. Verificaciones no realizadas

- Inspeccioné visualmente los PNG actuales: ambos muestran los bucles y decisiones que aparecen en las fuentes actualizadas. No hice una comparación binaria ni regeneré las imágenes, así que no puedo certificar que se hayan producido desde esos `.puml` exactos; la inspección visual sí confirma correspondencia aparente.
- No puedo verificar el código originalmente generado por la IA a partir del registro actual: ese output fuente no está incluido.
- No ejecuté el renderizador PlantUML ni validé sintácticamente los diagramas mediante una herramienta externa.

## E. Comentario propuesto para GitHub

> Gracias por las correcciones: los bucles de validación y el orden de confirmación en CU2 ya reflejan mejor los escenarios. Antes de aprobar, sugiero ajustar tres puntos: en CU1, que elegir otro producto vuelva a la selección y que descartar termine sin registrar el pedido; calcular y presentar el total antes de confirmar el registro; y en CU2, volver a verificar que el estado siga siendo `recibido` antes de persistir. También convendría corregir las rutas de contexto en el registro de IA y añadir los escenarios alternativos consultados. Como mejora documental, se puede incluir el output PlantUML original para que las iteraciones queden verificables.

**Conclusión:** hay hallazgos anteriores resueltos, pero permanecen defectos importantes en las ramas de producto no disponible y en el orden del total de CU1, además de faltar la comprobación del estado durante la edición en CU2. **El PR requiere correcciones antes de aprobarse.**

### Evaluación y ajustes humanos

La segunda revisión del PR #193 se realizó sobre los cambios incorporados entre los commits `ec2f36f` y `51a8cbb`, con el objetivo de comprobar las correcciones solicitadas en la primera revisión y detectar posibles inconsistencias nuevas.

**Hallazgos aceptados y verificados:**

- **CU1 — Validación de datos:** se comprobó que el nuevo bucle permite corregir y volver a validar los datos antes de continuar con el registro. Se consideró resuelto el hallazgo original.
- **CU1 — Producto no disponible:** se incorporó la decisión correspondiente, pero se verificó que elegir otro producto no conduce a una nueva comprobación de disponibilidad y que descartar no interrumpe el registro. Se mantuvo como corrección pendiente.
- **CU2 — Revalidación de reglas:** se comprobó que el nuevo bucle permite ajustar los cambios y volver a validar las reglas de negocio. Se consideró resuelto.
- **CU2 — Orden de confirmación:** se verificó que el sistema recalcula y muestra el nuevo total antes de solicitar la confirmación. Se consideró resuelto.
- **CU1 — Total antes de confirmar:** se aceptó el hallazgo de Copilot al contrastar el orden de las actividades con el escenario principal de A2. Se solicitó calcular y mostrar el total final antes de confirmar el pedido.
- **CU2 — Cambio de estado durante la edición:** se verificó en `diagramas/02-casos-de-uso/02-modificar-pedido.puml` que el caso de uso contempla rechazar una modificación cuando el pedido cambia de estado durante la edición. Se aceptó la observación de Copilot y se solicitó una nueva comprobación antes de persistir los cambios.

**Evaluación de documentación:**

- Se reconoció la incorporación de iteraciones y una respuesta textual de IA en `ia/a3/esp-actividades-1-2.md`.
- Se mantuvo la observación sobre las rutas incorrectas de los escenarios de A2 y la necesidad de completar o aclarar la disponibilidad del output original de IA.
- Se comprobó que el autor incorporó su contribución en `changelog.md`. Como ajuste de organización, se recomendó mantenerla dentro de `Unreleased → Added`, sin crear un encabezado de release adicional.

**Ajustes humanos antes de publicar:**

La propuesta de Copilot se reformuló en comentarios breves y específicos, vinculados con las líneas correspondientes de los diagramas PlantUML. Se diferenciaron los tres problemas técnicos que requerían corrección de las observaciones documentales, que se incluyeron en el comentario general.

Se evitó repetir los hallazgos ya resueltos como errores pendientes. La decisión humana fue solicitar nuevamente cambios, dado que persistían inconsistencias con los escenarios y reglas de negocio de A2.

La revisión se publicó en GitHub mediante tres comentarios inline y un comentario general, con la decisión Request changes.

### Revisión publicada en GitHub

- **Enlace a la revisión:** [PR #193 — segunda revisión](https://github.com/lucasmengarelli3/SistemaPedidos/pull/193)
- **Decisión:** Request changes.
- **Correcciones solicitadas:**
  1. CU1: separar los caminos de producto no disponible, permitiendo volver a seleccionar y validar otro producto o descartar el pedido sin registrarlo.
  2. CU1: calcular y mostrar el total final antes de confirmar el pedido.
  3. CU2: volver a verificar que el pedido permanezca en estado `recibido` antes de persistir las modificaciones.
  4. Documentación de IA: corregir las rutas de los escenarios de A2 y completar o aclarar el output original.
  5. Changelog: mantener la contribución dentro de `Unreleased → Added`.
- **Resultado final:** Segunda revisión del PR #193 publicada el 21/10/2026 mediante tres comentarios inline y un comentario general. Se reconocieron las correcciones realizadas, pero se solicitaron nuevos ajustes antes de aprobar el PR.

---

## Revisión 4

**PR:** [#190](https://github.com/lucasmengarelli3/SistemaPedidos/pull/190) — Segunda revisión de las correcciones

**Autor:** @lucasmengarelli3 (Lucas)

**Rol revisado:** Especialista en Diagramas de Actividades (CU3, CU4, CU5 y CU6)

**Fecha:** 22/10/2026

**Estado:** Revisión publicada — Request changes

### Archivos de contexto

- Diagramas de actividades CU3, CU4, CU5 y CU6, en formato `.puml` y `.png`.
- Versiones de los commits `2d9518b` y `e6c5734`.
- Casos de uso y escenarios de la Actividad Obligatoria N.º 2.
- `ia/a3/esp-actividades-3-4-5.md`.
- `changelog.md`.
- Observaciones de la primera revisión del PR #190.

### Prompt utilizado

```text
Actuá como revisor técnico de UML y documentación del proyecto académico SistemaPedidos.

Necesito realizar la **segunda revisión asistida por IA del Pull Request #190**, correspondiente a los diagramas de actividades de los casos de uso CU3, CU4, CU5 y CU6.

**Repositorio:** `lucasmengarelli3/SistemaPedidos`

**Rama del PR:** `feature/esp-actividades-3-4-5-add-diagrama-actividad-3`

**Commits a comparar:**

- Versión anterior: `2d9518b`
- Versión corregida: `e6c5734`
**Objetivo:** comprobar si Lucas resolvió las observaciones de mi primera revisión y si sus cambios introdujeron nuevas inconsistencias.

### Contexto obligatorio
Consultá los archivos reales de ambas versiones, los cuatro diagramas `.puml`, sus PNG, los casos de uso y escenarios correspondientes de A2, `ia/a3/esp-actividades-3-4-5.md` y `changelog.md`.

No utilices los archivos de secuencia de la rama de trabajo actual. La revisión corresponde exclusivamente al PR #190.

### Hallazgos de la primera revisión

1. CU3: la consulta y selección del pedido estaban asignadas a mostrador en lugar de Cocina; faltaba una decisión ante un estado inválido.
2. CU4: el sistema decidía si el pago estaba autorizado antes de recibir el resultado del medio de pago.
3. CU5: se registraba la entrega antes de la entrega física y su confirmación.
4. CU6: faltaba la confirmación explícita del usuario después de validar el estado; la notificación a Cocina no estaba correctamente condicionada.
5. Los PNG mostraban caracteres acentuados incorrectamente.
6. La documentación de IA tenía inconsistencias y no detallaba suficientemente las iteraciones.

### Instrucciones

1. Compará los commits `2d9518b` y `e6c5734`, sin modificar archivos.
2. Clasificá cada hallazgo anterior como **resuelto, parcialmente resuelto o pendiente**, con evidencia concreta.
3. Revisá especialmente:

- CU3: si Cocina visualiza el detalle antes de que el sistema lo busque y cargue.
- CU4: si un pago rechazado puede continuar hacia la emisión del comprobante y si el reintento vuelve realmente a validar.
- CU5: si el registro de entrega ocurre después de la entrega y confirmación humanas.
- CU6: si Cocina interrumpe la preparación únicamente cuando el pedido estaba `en preparación`.
4. Verificá si los PNG reflejan los `.puml` actualizados y muestran correctamente los caracteres.
5. Revisá los cambios en la documentación de IA y el changelog.
6. Identificá regresiones o problemas nuevos.
7. Diferenciá errores confirmados de mejoras opcionales.
8. No modifiques archivos, no hagas commits, no publiques comentarios, no apruebes ni hagas merge.

### Formato de respuesta
**A. Tabla de hallazgos anteriores:** estado, evidencia y justificación.

**B. Problemas pendientes o nuevos:** archivo, ubicación, gravedad y explicación.

**C. Documentación y PNG:** resultado de las verificaciones.

**D. Verificaciones no realizadas:** indicar expresamente lo que no pudiste comprobar.

**E. Comentarios propuestos para GitHub:** breves, respetuosos y accionables.

**F. Conclusión:** indicar si el PR está listo para aprobarse o requiere correcciones.

No inventes evidencia. Si no podés acceder a alguna versión, archivo o imagen, informalo expresamente.
```

### Output obtenido

## A. Hallazgos anteriores

| Hallazgo | Estado | Evidencia y justificación |
|---|---|---|
| **CU3: consulta/selección asignadas al carril incorrecto y falta de decisión ante estado inválido** | **Resuelto**, con una inconsistencia nueva | En [CU3 `.puml`](https://github.com/lucasmengarelli3/SistemaPedidos/blob/e6c5734410731ac7b1360828d16f04416a2b63e8/diagramas/04-diagramas-actividades/04-actividad-preparar-pedido-03.puml#L21-L38), Cocina consulta la cola y selecciona el pedido; el sistema ahora decide si el estado es `recibido` y detiene el flujo si no. Sin embargo, Cocina visualiza el detalle antes de que el sistema busque y cargue el pedido —ver problemas nuevos abajo. |
| **CU4: se decidía si el pago estaba autorizado antes de recibir el resultado del medio** | **Resuelto** | En [CU4 `.puml`](https://github.com/lucasmengarelli3/SistemaPedidos/blob/e6c5734410731ac7b1360828d16f04416a2b63e8/diagramas/04-diagramas-actividades/04-actividad-cobrar-cuenta-04.puml#L28-L45), el sistema solicita la autorización, el medio de pago devuelve su resultado y recién después se decide si fue aprobado. El reintento, no obstante, no vuelve efectivamente a la validación. |
| **CU5: registro de entrega previo a la entrega física y su confirmación** | **Resuelto en cuanto al orden** | En [CU5 `.puml`](https://github.com/lucasmengarelli3/SistemaPedidos/blob/e6c5734410731ac7b1360828d16f04416a2b63e8/diagramas/04-diagramas-actividades/04-actividad-entregar-pedido-05.puml#L40-L50), la entrega y confirmación humanas preceden a `Registra la entrega en historial`. Queda una asignación incorrecta de responsabilidades: `Registra responsable y fecha` está en un carril humano combinado. |
| **CU6: faltaba confirmación explícita y la notificación a Cocina no estaba condicionada** | **Parcialmente resuelto** | En [CU6 `.puml`](https://github.com/lucasmengarelli3/SistemaPedidos/blob/e6c5734410731ac7b1360828d16f04416a2b63e8/diagramas/04-diagramas-actividades/04-actividad-cancelar-pedido-06.puml#L26-L51), el estado se valida, luego el Usuario confirma y la actividad que notifica a Cocina está condicionada a que el pedido estuviera `en preparación`. Pero la actividad posterior de Cocina `Interrumpe la preparación` queda fuera de esa decisión y se ejecuta también si el pedido estaba solo `recibido`. |
| **PNG con caracteres acentuados incorrectos** | **Resuelto** | Comparé las imágenes de `2d9518b` con las de `e6c5734`: las anteriores mostraban texto mojibake —por ejemplo, `preparaciÃ³n`— y las actuales muestran los acentos correctamente en los cuatro diagramas. |
| **Documentación de IA inconsistente y sin detalle suficiente de iteraciones** | **Parcialmente resuelto** | Se agregó una sección de iteraciones en [documentación de IA](https://github.com/lucasmengarelli3/SistemaPedidos/blob/e6c5734410731ac7b1360828d16f04416a2b63e8/ia/a3/esp-actividades-3-4-5.md), pero se limita a mencionar duplicación/nombres cruzados y correcciones solicitadas por el coordinador; no registra qué cambios concretos se hicieron en cada iteración. Persisten inconsistencias en el título y en el prompt transcripto. |

## B. Problemas pendientes o nuevos

1. **Importante — CU3, orden de consulta y carga del detalle.**  
   En [CU3 `.puml`, actividad de Cocina y búsqueda del sistema](https://github.com/lucasmengarelli3/SistemaPedidos/blob/e6c5734410731ac7b1360828d16f04416a2b63e8/diagramas/04-diagramas-actividades/04-actividad-preparar-pedido-03.puml#L21-L30), `Visualiza el pedido y su detalle` aparece antes de `Busca el pedido por identificador` y `Carga detalle del pedido y personalizaciones`. El PNG refleja ese orden. Esto deja la visualización antes de que el flujo haya encontrado y cargado los datos. Además, es una regresión respecto a `2d9518b`, donde la visualización estaba después de la búsqueda y carga.

2. **Importante — CU4, reintento de pago no regresa a la validación.**  
   En [CU4 `.puml`](https://github.com/lucasmengarelli3/SistemaPedidos/blob/e6c5734410731ac7b1360828d16f04416a2b63e8/diagramas/04-diagramas-actividades/04-actividad-cobrar-cuenta-04.puml#L43-L58), el camino de rechazo contiene `Solicita otro medio de pago` y `Retoma desde la validación de la operación`, pero no tiene una transición que vuelva al medio de pago o a `Solicita autorización`. Las ramas se reúnen y continúan hacia `Entrega comprobante al cliente`; por tanto, un rechazo puede alcanzar el comprobante sin un nuevo intento aprobado. El PNG confirma la misma convergencia. El escenario alternativo de A2 especifica que el reintento vuelve al paso de autorización, sin registrar el pago rechazado.

3. **Importante — CU5, carriles de entrega y registro de responsable.**  
   En [CU5 `.puml`](https://github.com/lucasmengarelli3/SistemaPedidos/blob/e6c5734410731ac7b1360828d16f04416a2b63e8/diagramas/04-diagramas-actividades/04-actividad-entregar-pedido-05.puml#L40-L48), se usa un solo carril `Mostrador / Cliente` para entregar, confirmar y registrar responsable/fecha. A2 asigna la entrega y confirmación al Usuario de mostrador, y el registro de estado, fecha y responsable al sistema. El cambio corrigió el orden temporal de la actividad del sistema, pero no separó esas responsabilidades. No es un problema de secuencia —la confirmación precede al registro del historial—, sino de asignación y claridad de los carriles.

4. **Importante — CU6, interrupción de Cocina no condicionada.**  
   En [CU6 `.puml`](https://github.com/lucasmengarelli3/SistemaPedidos/blob/e6c5734410731ac7b1360828d16f04416a2b63e8/diagramas/04-diagramas-actividades/04-actividad-cancelar-pedido-06.puml#L47-L56), la decisión condiciona la notificación, pero luego ambas ramas convergen antes de que Cocina `Interrumpe la preparación`. Si el estado era `recibido`, Cocina no debería recibir aviso ni ejecutar una interrupción. El PNG muestra esa actividad fuera de la rama afirmativa. Esto empeoró respecto a la versión anterior, que al menos rotulaba la interrupción como condicional.

5. **Menor — changelog con ruta de documentación incorrecta.**  
   La entrada actual de [changelog.md](https://github.com/lucasmengarelli3/SistemaPedidos/blob/e6c5734410731ac7b1360828d16f04416a2b63e8/changelog.md#L13) referencia `ia/a3/esp-actividades-3-4-5-6`, pero el archivo entregado por el PR es `ia/a3/esp-actividades-3-4-5.md`. La versión anterior enlazaba el nombre sin `-6`, de modo que el cambio introdujo el desajuste. La entrada sí registra las issues y el PR; como recomendación menor, podría incluir también la persona y el rol, dado que la descripción del changelog menciona participación y roles.

## C. Documentación y PNG

- **Imágenes:** los cuatro PNG están modificados en `e6c5734`. Los inspeccioné visualmente y sus acciones corresponden a las fuentes `.puml` actuales; los caracteres acentuados se ven correctamente. También reflejan los problemas de flujo señalados en CU3, CU4 y CU6. No hice una comparación binaria ni regeneré las imágenes.
- **Documentación de IA:** registra el prompt, una lista de contexto, los outputs y ajustes. La sección nueva de iteraciones no permite reconstruir qué observación produjo cada corrección ni qué se cambió en respuesta. El título todavía dice “Casos de uso 3, 4 y 5” aunque cubre también CU6. El prompt contiene nombres de salida equivocados para los PNG de cobro y cancelación; la lista de outputs posterior sí usa los nombres correctos.
- **Changelog:** la entrada está bajo la sección de actividad/unreleased y enlaza PR/issues, pero la ruta de IA es incorrecta. No considero que la jerarquía de encabezados sea un defecto: coincide con la estructura de releases anterior del archivo.

## D. Verificaciones no realizadas

- No ejecuté PlantUML ni regeneré los PNG. La comprobación de correspondencia y acentos fue visual, junto con la inspección de las fuentes y del cambio de archivos en el commit.
- No comprobé equivalencia binaria entre cada PNG y una renderización fresca de su fuente.

Sí pude consultar ambas versiones de los cuatro diagramas, los PNG previos y corregidos, las fuentes de casos de uso y escenarios A2, la documentación de IA y el changelog. La revisión se limitó al PR #190; no usé los diagramas de secuencia de la rama de trabajo.

## E. Comentarios propuestos para GitHub

- **CU3:** “¿Podrían mover `Visualiza el pedido y su detalle` después de buscar el pedido y cargar su detalle? En el flujo actual Cocina ve información antes de que el sistema la recupere.”
- **CU4:** “¿Podrían conectar el reintento con una nueva solicitud de autorización/validación y evitar que la rama rechazada se reúna con la emisión del comprobante? Actualmente el rechazo también puede llegar a `Entrega comprobante al cliente`.”
- **CU5:** “¿Podrían separar `Cliente` y `Usuario de mostrador` en carriles distintos y ubicar el registro de responsable/fecha en el sistema? A2 atribuye la entrega y confirmación al usuario, y el registro al sistema.”
- **CU6:** “¿Podrían hacer que la actividad de Cocina `Interrumpe la preparación` solo se alcance cuando el estado previo era `en preparación`? En el flujo actual la notificación está condicionada, pero la interrupción se ejecuta después de la convergencia.”
- **Documentación:** “¿Podrían detallar las iteraciones/correcciones concretas en el registro de IA y corregir en el changelog el enlace a `ia/a3/esp-actividades-3-4-5.md`?”

## F. Conclusión

**El PR requiere correcciones antes de aprobarse.** Se resolvieron varias observaciones anteriores —incluido el orden del resultado de autorización en CU4, la confirmación de CU6 y la codificación de los PNG—, pero siguen presentes errores funcionales en el reintento de cobro y la condición de interrupción de Cocina, además del orden de visualización en CU3. También quedan ajustes de responsabilidad y documentación.

### Evaluación y ajustes humanos

Se contrastaron los hallazgos de Copilot con los archivos del PR, en particular los flujos de CU3, CU4, CU5 y CU6.

Se confirmó que las correcciones anteriores resolvieron parte de los problemas, pero no eliminaron todas las inconsistencias funcionales.

En CU5 se examinó el bloque `Mostrador / Cliente` y se confirmó que la entrega, la confirmación y el registro de responsable y fecha estaban agrupados en un mismo carril, pese a corresponder a participantes distintos.

También se verificó que `changelog.md` referencia `ia/a3/esp-actividades-3-4-5-6`, mientras que el archivo existente se denomina `ia/a3/esp-actividades-3-4-5.md`.

La evaluación humana distinguió los errores funcionales de las observaciones documentales. Se reconocieron expresamente las correcciones realizadas por el autor y no se solicitaron cambios adicionales sobre los aspectos ya resueltos.

No se modificaron archivos del PR durante la revisión ni se realizaron commits o merges. La decisión de solicitar cambios fue humana, basada en la evidencia técnica y no únicamente en la respuesta de Copilot.

### Revisión publicada en GitHub

- **Enlace a la revisión:** [PR #190 — conversación y revisiones](https://github.com/lucasmengarelli3/SistemaPedidos/pull/190)
- **Decisión:** Request changes.
- **Correcciones solicitadas:** Ajustar el orden de visualización en CU3, representar un reintento real de autorización en CU4, separar responsabilidades en CU5, condicionar la interrupción de Cocina en CU6 y corregir la trazabilidad documental.
- **Resultado final:** Segunda revisión publicada con cinco observaciones en línea y comentario general. El PR permanece pendiente de correcciones y no fue aprobado en esta revisión.

---

## Resumen de revisiones

| Revisión | PR | Rol revisado | Hallazgos validados | Decisión humana | Enlace |
| --- | --- | --- | --- | --- | --- |
| 1 | #190 | Especialista en Diagramas de Actividades (CU3–6) | Flujos de preparación, cobro, entrega y cancelación; codificación de PNG; registro de IA | Request changes | [PR #190](https://github.com/lucasmengarelli3/SistemaPedidos/pull/190) |
| 2 | #193 | Especialista en Diagramas de Actividades (CU1–2) | Validaciones y caminos alternativos de CU1 y CU2; orden de confirmación; changelog y registro de IA | Request changes | [PR #193](https://github.com/lucasmengarelli3/SistemaPedidos/pull/193) |
| 3 | #193 (segunda revisión) | Especialista en Diagramas de Actividades (CU1–2) | Correcciones de validación verificadas; producto no disponible, cálculo del total en CU1 y cambio de estado en CU2; documentación de IA | Request changes | [PR #193](https://github.com/lucasmengarelli3/SistemaPedidos/pull/193) |
| 4 | #190 (segunda revisión) | Especialista en Diagramas de Actividades (CU3–6) | Correcciones verificadas y errores pendientes de flujo, responsabilidades y documentación | Request changes | [PR #190](https://github.com/lucasmengarelli3/SistemaPedidos/pull/190) |

## Conclusiones

Se realizaron cuatro revisiones de código asistidas por GitHub Copilot sobre los PR #190 y #193, correspondientes a los diagramas de actividades de los seis casos de uso de SistemaPedidos.

La IA se utilizó para analizar diagramas PlantUML, comparar versiones, identificar inconsistencias en los flujos, verificar la asignación de responsabilidades y revisar la trazabilidad documental. Las revisiones posteriores permitieron comprobar qué observaciones habían sido resueltas y detectar problemas nuevos introducidos durante las correcciones.

Los resultados de Copilot no se adoptaron automáticamente. Cada revisión incluyó evaluación humana de los hallazgos, contraste con los archivos del repositorio y selección de observaciones justificadas. También se tuvieron en cuenta las limitaciones declaradas por la herramienta, especialmente cuando no se ejecutaron validaciones automáticas o no se regeneraron imágenes.

Las cuatro revisiones concluyeron con solicitudes de cambios porque se identificaron inconsistencias que requerían intervención de sus respectivos autores. Se publicaron observaciones específicas en GitHub para facilitar las correcciones.

La experiencia permitió utilizar la IA como apoyo al control de calidad sin delegarle la responsabilidad de aprobar cambios, modificar el repositorio ni decidir su integración. Las decisiones finales permanecieron bajo supervisión humana.