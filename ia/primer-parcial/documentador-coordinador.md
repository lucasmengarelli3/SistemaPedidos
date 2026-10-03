# Documentador y Coordinador de Repositorio - Uso de IA

## Herramienta utilizada

Se utilizó Claude Code (modelo Claude Opus) en modo agente dentro de VS Code. La consigna menciona Copilot Agent Mode; se trabajó con Claude Code porque cumple la misma función: lee los archivos del repositorio indicados como contexto y propone los hallazgos, que luego se revisan de forma crítica antes de publicarlos.

El uso de IA para el análisis del principio SRP está documentado en [especialista-srp.md](./especialista-srp.md).

## Prompt utilizado

Se adjuntó la consigna del Primer Parcial en PDF y se ingresó el siguiente mensaje:

> soy documentador y coordinador podes corregir lo que me falta

A partir de la consigna adjunta (segunda tarea del rol), el agente revisó cada PR abierta con el formato de revisión que el equipo definió en la Actividad Obligatoria N°2 ([ia/a2/documentador-coordinador.md](../a2/documentador-coordinador.md)). En cada revisión, `{ROL_REVISADO}` se reemplazó por el rol dueño del entregable:

- Especialista en Principios de Extensión (OCP)
- Especialista en Principios de Extensión (LSP)
- Especialista en Segregación de Interfaces (ISP)
- Especialista en Inversión de Dependencias (DIP)

~~~~markdown
# Estás analizando los cambios de una Pull Request activa en el repositorio del equipo

## CONTEXTO DEL PROYECTO

- Actúas como el Documentador y Coordinador de Repositorio, revisando el entregable del rol: {ROL_REVISADO}
- Antes de generar hallazgos, lee anexos/introduccion.md del repositorio para conocer los requisitos y casos de uso definidos en la Actividad Obligatoria N°1. Usa ese
  contenido como criterio de referencia para evaluar coherencia.
- Verifica que la PR incluya el archivo ia/primer-parcial/[rol].md con prompt utilizado, archivos de contexto referenciados, output obtenido y ajustes realizados.

## INSTRUCCIONES IMPORTANTES

- Identifica problemas reales del código o del entregable (incluye inconsistencias
  respecto a anexos/introduccion.md como un tipo de hallazgo válido)
- Enumera los hallazgos (1, 2, 3…)
- Cada hallazgo debe ser independiente
- Sé claro, técnico y concreto
- No inventes problemas hipotéticos sin evidencia en el código o en el documento
- No incluyas sugerencias de tests

Para cada hallazgo usa EXACTAMENTE esta estructura:

==================================================
HALLAZGO #<número>

Archivo:
Línea:

Tipo de problema:
(bug | performance | seguridad | legibilidad | diseño | coherencia con requisitos | otro)

Severidad:
(baja | media | alta | crítica)

Explicación técnica:
Por qué esto es un problema real.

Sugerencia de mejora:
Cambio concreto recomendado.

Ejemplo de código corregido (si aplica):

```codigo
ejemplo
```

DECISIÓN DEL REVISOR HUMANO:

[ ] Aceptar sugerencia
[ ] Rechazar sugerencia

Justificación del revisor humano:
(Completar manualmente si se rechaza)
==================================================

Al final agrega:

==================================================
RESUMEN GENERAL DE LA PR

Evaluación global de calidad, riesgos técnicos y coherencia con anexos/introduccion.md.

DECISIÓN FINAL SUGERIDA POR IA:

# APPROVE / REQUEST CHANGES / COMMENT ONLY

No completes la sección "DECISIÓN DEL REVISOR HUMANO". Debe quedar vacía para edición manual.
~~~~

## Archivos de contexto referenciados

- [Requisitos, estados del pedido y casos de uso](../../anexos/introduccion.md): criterio de referencia para evaluar la coherencia de cada entregable.
- [Boceto inicial de clases](../../diagramas/01-diagrama-clases/01-boceto-inicial-corregido.excalidraw) y [tarjetas CRC](../../herramientas-agile/tarjetas-crc/tarjetas-crc.md): para verificar que las clases, atributos y métodos citados en cada anexo existan en el diseño.
- [Anexo SRP](../../anexos/principios-solid/01-srp.md) y [anexo OCP](../../anexos/principios-solid/02-ocp.md), ya integrados en `develop`: para verificar que los anexos de los distintos principios describan un mismo diseño.
- Los archivos modificados en cada PR revisada (ver tabla siguiente).

## Output obtenido

| PR | Rol revisado | Archivos revisados | Hallazgos (severidad) | Decisión sugerida por IA | Decisión del revisor humano | Revisión |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| [#144](https://github.com/lucasmengarelli3/SistemaPedidos/pull/144) | Especialista en Principios de Extensión (OCP) | `02-ocp.md`, `01-solid-02-ocp.puml`, `especialista-ocp.md` y `changelog.md` | 6 (3 media, 3 baja) | REQUEST CHANGES | 6 aceptados; correcciones entregadas en la PR #146 | [Hallazgos #1, #2 y #6 y resumen](https://github.com/lucasmengarelli3/SistemaPedidos/pull/144#pullrequestreview-5392681284), [hallazgos #3, #4 y #5](https://github.com/lucasmengarelli3/SistemaPedidos/pull/144#pullrequestreview-5392474411) |
| [#146](https://github.com/lucasmengarelli3/SistemaPedidos/pull/146) | Especialista en Principios de Extensión (OCP), corrección de hallazgos | `02-ocp.md`, `01-solid-02-ocp.puml`, `especialista-ocp.md` y `changelog.md` | 6 (5 media, 1 baja) | REQUEST CHANGES | 6 aceptados; el commit `67d041f` resolvió parte del hallazgo #6 y la PR se aprobó y se mergeó; los hallazgos restantes los aplicó el coordinador en la PR [#157](https://github.com/lucasmengarelli3/SistemaPedidos/pull/157) | [Ver revisión](https://github.com/lucasmengarelli3/SistemaPedidos/pull/146#pullrequestreview-5398915526), [aprobación](https://github.com/lucasmengarelli3/SistemaPedidos/pull/146#pullrequestreview-5402377521) |
| [#148](https://github.com/lucasmengarelli3/SistemaPedidos/pull/148) | Especialista en Segregación de Interfaces (ISP) | `04-isp.md`, `01-solid-04-isp.puml`, `especialista-isp.md` y `changelog.md` | 4 (2 media, 2 baja) | REQUEST CHANGES | 4 aceptados; correcciones entregadas en el commit `0416f2b`, PR aprobada y mergeada | [Ver revisión](https://github.com/lucasmengarelli3/SistemaPedidos/pull/148#pullrequestreview-5398915667), [aprobación](https://github.com/lucasmengarelli3/SistemaPedidos/pull/148#pullrequestreview-5399215533) |
| [#150](https://github.com/lucasmengarelli3/SistemaPedidos/pull/150) | Especialista en Inversión de Dependencias (DIP) | `05-dip.md`, `01-solid-05-dip.puml`, `especialista-dip.md` y `changelog.md` | 6 (1 alta, 2 media, 3 baja) | REQUEST CHANGES | 6 aceptados; correcciones entregadas en el commit `5d11675` | [Ver revisión](https://github.com/lucasmengarelli3/SistemaPedidos/pull/150#pullrequestreview-5398915875) |
| [#150](https://github.com/lucasmengarelli3/SistemaPedidos/pull/150) | Especialista en Inversión de Dependencias (DIP), verificación de las correcciones | `05-dip.md`, `01-solid-05-dip.puml` y `especialista-dip.md` | 4 (1 alta, 2 media, 1 baja) | REQUEST CHANGES | 4 aceptados; correcciones aplicadas por el coordinador en el commit `53cd8b2` | [Ver revisión](https://github.com/lucasmengarelli3/SistemaPedidos/pull/150#pullrequestreview-5401291580) |
| [#150](https://github.com/lucasmengarelli3/SistemaPedidos/pull/150) | Especialista en Inversión de Dependencias (DIP), revisión final | `05-dip.md`, `01-solid-05-dip.puml`, `01-solid-05-dip.png` y `especialista-dip.md` | Sin hallazgos | APPROVE | PR aprobada y mergeada | [Ver revisión](https://github.com/lucasmengarelli3/SistemaPedidos/pull/150#pullrequestreview-5401339487) |
| [#155](https://github.com/lucasmengarelli3/SistemaPedidos/pull/155) | Especialista en Principios de Extensión (LSP) | `03-lsp.md`, `01-solid-03-lsp.puml`, `01-solid-03-lsp.png`, `especialista-lsp.md` y `changelog.md` | 6 (4 media, 2 baja) | REQUEST CHANGES | 6 aceptados; correcciones pendientes | [Ver revisión](https://github.com/lucasmengarelli3/SistemaPedidos/pull/155#pullrequestreview-5402592203) |

La revisión de la PR #144 se realizó en una sesión anterior con el mismo formato. Las verificaciones de las correcciones de las PRs #146, #148 y #150 y la revisión de la PR #155 se hicieron en sesiones posteriores, también con el mismo formato.

Fragmento representativo de la respuesta (PR #150, hallazgo #1):

> La consigna define cinco secciones para `05-dip.md` [...]. El anexo usa otros encabezados [...]. Además falta contenido obligatorio: en ningún lugar se explica qué es una clase abstracta ni qué es una interfaz, que son dos tareas específicas del rol y un ítem de la rúbrica.

Los hallazgos predominantes fueron de dos tipos:

- **Coherencia entre anexos.** El anexo SRP quitó `registrarPago()` y `calcularTotal()` de `Pedido`. Los diagramas de ISP y DIP parten del boceto inicial y los conservan, y el de DIP agrega `GestorPago`, que se superpone con `RegistradorPago`.
- **Cumplimiento de la consigna.** Secciones de los anexos y de los archivos `ia/primer-parcial/[rol].md` que no coinciden con las pedidas, y enlaces a la imagen del diagrama.

## Ajustes realizados

Cada hallazgo se contrastó con los archivos de la PR, el boceto, las tarjetas CRC y `anexos/introduccion.md` antes de darlo por válido:

- **Hallazgo descartado en la PR #148.** El agente evaluó señalar que el diagrama ISP no indica tipos en atributos ni métodos. Se descartó porque el boceto inicial tampoco los indica y el diagrama reproduce sus nombres tal como figuran allí.
- **Hallazgo reformulado en la PR #148.** El anexo ISP afirma que el modelo no tiene clases cliente de las interfaces. Se verificó contra el boceto que sí existen (`PersonalAtencion.modificarPedido()`, `Cocina.marcarPedidoListo()`, `Encargado.cambiarEstadoPedido()`), y el hallazgo se redactó citando esos métodos y los casos de uso "Registrar pedido" y "Preparar pedido".
- **Verificación de las correcciones de la PR #146.** Se comparó cada hallazgo de la PR #144 con el diff de la PR #146. Tres quedaron resueltos y tres incompletos, y se detectó un cambio nuevo que no estaba pedido (la asociación de `GestorPedidos` con la clase concreta `CocinaInterna`).
- **Atributo de retiro.** El diagrama DIP usa `referenciaRetiro` y el anexo SRP usa `nombreRetiro`. No se cargó como hallazgo porque ambos nombres tienen respaldo: el primero figura en la tarjeta CRC de `Pedido` y el segundo en el boceto.
- **Verificación de las correcciones de la PR #148.** Se comprobó en `develop` que los cuatro hallazgos quedaran resueltos: el diagrama muestra los clientes de cada interfaz (`GestorPedidos`, `Cocina` y `Encargado`), se quitó `ICobroPedido`, hay una nota por interfaz, la imagen enlaza al PNG y el prompt está en un bloque de código.
- **Verificación de las correcciones de la PR #150.** Se comparó el commit `5d11675` con la versión revisada antes. Los seis hallazgos estaban resueltos, pero la comparación mostró tres problemas nuevos que el diff por sí solo no evidenciaba: la Motivación atribuía al boceto dependencias de persistencia y cobro que no tiene, el anexo había perdido la tabla de dependencias y la de inyección por constructor, y el texto del "Prompt utilizado" había cambiado respecto del original.
- **Correcciones aplicadas por el coordinador en la PR #150.** Los cuatro hallazgos de la segunda revisión se corrigieron en el commit `53cd8b2` sobre la rama del especialista: se recuperó el contenido de la versión anterior del anexo, se restauró el prompt original y se regeneró el PNG del diagrama. El aporte original y la corrección de la primera revisión son del especialista.
- **Verificación de las correcciones de la PR #146 después del merge.** Se comparó `develop` con los seis hallazgos de la revisión. Solo estaba resuelta una parte del #6 (el nombre de la rama y la sección `### Fixed` del changelog); los hallazgos #1 a #5 seguían presentes porque la PR se aprobó y se mergeó sin esos cambios.
- **Correcciones aplicadas por el coordinador en la PR #157.** Los hallazgos pendientes de la PR #146 se corrigieron en una rama nueva: se invirtió la dependencia entre `RegistradorPago` y `Pedido`, se quitó la asociación de `GestorPedidos` con `CocinaInterna`, se indicó qué clase depende de cada abstracción, se ordenó el documento de IA y se regeneró el PNG del diagrama. El aporte original es del especialista. Queda a confirmar por el especialista cuál de los dos prompts de `especialista-ocp.md` es el texto literal.
- **Revisión de la PR #155.** Antes de cargar el hallazgo del changelog se simuló el merge con `develop`, lo que mostró que las entradas del ISP y del DIP quedaban duplicadas; el diff de la PR por sí solo no lo evidenciaba. La dependencia invertida entre `Pedido` y `RegistradorPago` se cargó como hallazgo porque repite el problema ya señalado en el diagrama del OCP.
- **Verificación del archivo de IA.** En las cinco PRs se comprobó que existiera `ia/primer-parcial/[rol].md` con sus cuatro puntos. En las PRs #144, #146, #150 y #155 se cargaron hallazgos por secciones faltantes o mal ubicadas.
