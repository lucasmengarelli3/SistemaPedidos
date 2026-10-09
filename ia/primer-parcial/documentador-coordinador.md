# Documentador y Coordinador de Repositorio - Uso de IA

## Herramienta utilizada

Se utilizó Claude Code (modelo Claude Opus) en modo agente dentro de VS Code. La consigna menciona Copilot Agent Mode; se trabajó con Claude Code porque cumple la misma función: lee los archivos del repositorio indicados como contexto y propone los hallazgos, que luego se revisan de forma crítica antes de publicarlos.

El uso de IA para el análisis del principio SRP está documentado en [especialista-srp.md](./especialista-srp.md).

## Prompt utilizado

Se adjuntó la consigna del Primer Parcial en PDF y se ingresó el siguiente mensaje:

```text
soy documentador y coordinador podes corregir lo que me falta
```

A partir de la consigna adjunta (segunda tarea del rol), el agente revisó cada PR abierta con el formato de revisión que el equipo definió en la Actividad Obligatoria N°2 ([ia/a2/documentador-coordinador.md](../a2/documentador-coordinador.md)). En cada revisión, `{ROL_REVISADO}` se reemplazó por el rol dueño del entregable:

- Especialista en Principios de Extensión (OCP)
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
| [#146](https://github.com/lucasmengarelli3/SistemaPedidos/pull/146) | Especialista en Principios de Extensión (OCP), corrección de hallazgos | `02-ocp.md`, `01-solid-02-ocp.puml`, `especialista-ocp.md` y `changelog.md` | 6 (5 media, 1 baja) | REQUEST CHANGES | 6 aceptados; correcciones pendientes | [Ver revisión](https://github.com/lucasmengarelli3/SistemaPedidos/pull/146#pullrequestreview-5398915526) |
| [#148](https://github.com/lucasmengarelli3/SistemaPedidos/pull/148) | Especialista en Segregación de Interfaces (ISP) | `04-isp.md`, `01-solid-04-isp.puml`, `especialista-isp.md` y `changelog.md` | 4 (2 media, 2 baja) | REQUEST CHANGES | 4 aceptados; correcciones entregadas en el commit `0416f2b`, PR aprobada y mergeada | [Ver revisión](https://github.com/lucasmengarelli3/SistemaPedidos/pull/148#pullrequestreview-5398915667), [aprobación](https://github.com/lucasmengarelli3/SistemaPedidos/pull/148#pullrequestreview-5399215533) |
| [#150](https://github.com/lucasmengarelli3/SistemaPedidos/pull/150) | Especialista en Inversión de Dependencias (DIP) | `05-dip.md`, `01-solid-05-dip.puml`, `especialista-dip.md` y `changelog.md` | 6 (1 alta, 2 media, 3 baja) | REQUEST CHANGES | 6 aceptados; correcciones entregadas en el commit `5d11675` | [Ver revisión](https://github.com/lucasmengarelli3/SistemaPedidos/pull/150#pullrequestreview-5398915875) |
| [#150](https://github.com/lucasmengarelli3/SistemaPedidos/pull/150) | Especialista en Inversión de Dependencias (DIP), verificación de las correcciones | `05-dip.md`, `01-solid-05-dip.puml` y `especialista-dip.md` | 4 (1 alta, 2 media, 1 baja) | REQUEST CHANGES | 4 aceptados; correcciones aplicadas por el coordinador en el commit `53cd8b2` | [Ver revisión](https://github.com/lucasmengarelli3/SistemaPedidos/pull/150#pullrequestreview-5401291580) |
| [#150](https://github.com/lucasmengarelli3/SistemaPedidos/pull/150) | Especialista en Inversión de Dependencias (DIP), revisión final | `05-dip.md`, `01-solid-05-dip.puml`, `01-solid-05-dip.png` y `especialista-dip.md` | Sin hallazgos | APPROVE | PR aprobada y mergeada | [Ver revisión](https://github.com/lucasmengarelli3/SistemaPedidos/pull/150#pullrequestreview-5401339487) |

La revisión de la PR #144 se realizó en una sesión anterior con el mismo formato. Las verificaciones de las correcciones de las PRs #148 y #150 se hicieron en sesiones posteriores, también con el mismo formato.

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
- **Verificación del archivo de IA.** En las cuatro PRs se comprobó que existiera `ia/primer-parcial/[rol].md` con sus cuatro puntos. En las PRs #144, #146 y #150 se cargaron hallazgos por secciones faltantes o mal ubicadas.

## Corrección de RC10 y RC11 — trazabilidad posterior a la entrega

### RC10 — Participación en las correcciones de OCP y LSP

En la PR #146, Lucas realizó una primera corrección de los hallazgos detectados sobre OCP. La revisión posterior verificó que parte de esos hallazgos seguían pendientes. El coordinador realizó una corrección adicional en la PR #157 mediante el commit `4cba8f1`, pero esa PR fue cerrada sin merge y dicho commit no quedó integrado en `release/primer-parcial`.

En la PR #155 se detectaron hallazgos pendientes sobre LSP. La PR #161 incluyó una corrección de esos hallazgos mediante el commit `71670d2`, pero fue cerrada sin merge y dicho commit no quedó integrado en `release/primer-parcial`.

Luego de los Request Changes del Primer Parcial, Lucas realizó nuevas correcciones sobre sus entregables. La corrección de OCP correspondiente a RC2 y RC3 quedó integrada mediante la PR #166, incluyendo el commit `72af049`. La corrección de LSP correspondiente a RC4 quedó integrada mediante la PR #164, incluyendo el commit `301ee85`.

Por lo tanto, las correcciones que actualmente forman parte de `release/primer-parcial` fueron realizadas e integradas posteriormente por el especialista responsable.

### RC11 — Cierre de PRs sin merge

Las PR #157, #159 y #161 fueron cerradas sin merge y sin dejar documentado en ese momento el motivo del cierre.

La PR #157 contenía correcciones pendientes de OCP realizadas por el coordinador. El commit de corrección `4cba8f1` quedó posteriormente incorporado en la rama utilizada por la PR #161, pero la PR #161 también fue cerrada sin merge. Por este motivo, dicho commit no quedó integrado en `release/primer-parcial`.

La PR #159 actualizaba la documentación de los code reviews de las PR #146 y #155 mediante el commit `8ab5bce`. Sus cambios también fueron incorporados en la rama de la PR #161, pero al cerrarse esta última sin merge, dicho commit no quedó integrado en `release/primer-parcial`.

La PR #161 integraba trabajo proveniente de las PR #157 y #159 y además incluía correcciones pendientes de LSP. El commit de corrección de LSP `71670d2` tampoco quedó integrado en `release/primer-parcial`, ya que la PR fue cerrada sin merge.

Posteriormente, las correcciones técnicas pendientes fueron realizadas nuevamente e integradas mediante las PR #164 y #166. La actualización documental que había quedado fuera mediante la PR #159 se registra ahora como parte de esta corrección de RC10 y RC11.

Se documenta esta secuencia para dejar explícita la trazabilidad de los cierres y de los cambios que finalmente quedaron integrados en `release/primer-parcial`.
