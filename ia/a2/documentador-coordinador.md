# Documentador y Coordinador de Repositorio

## Prompt utilizado

Se utilizó el mismo prompt para revisar las PRs de cada rol de la Actividad Obligatoria N°2. En cada revisión, `{ROL_REVISADO}` se reemplazó por el rol dueño del entregable:

- Diseñador de Tarjetas CRC
- Modelador de Diagramas de Casos de Uso
- Especialista en Escenarios de Casos de Uso

~~~~markdown
# Estás analizando los cambios de una Pull Request activa en el repositorio del equipo

## CONTEXTO DEL PROYECTO

- Actúas como el Documentador y Coordinador de Repositorio, revisando el entregable del rol: {ROL_REVISADO}
- Antes de generar hallazgos, lee anexos/introduccion.md del repositorio para conocer los requisitos y casos de uso definidos en la Actividad Obligatoria N°1. Usa ese
  contenido como criterio de referencia para evaluar coherencia.

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

Publica los comentarios directamente en la Pull Request en las líneas correspondientes.
No respondas en el chat salvo para el resumen final.
~~~~

## Archivos de contexto consultados

- [Contexto funcional, requisitos y casos de uso](../../anexos/introduccion.md): criterio de referencia para evaluar la coherencia de cada entregable.
- Los archivos modificados en cada PR revisada (ver tabla siguiente).

## Revisiones realizadas por el Documentador y Coordinador

Revisiones publicadas por @santimarM (Documentador y Coordinador) con el prompt anterior. Cada hallazgo se publicó como comentario en la línea correspondiente de la PR, con la decisión del revisor humano completada. Como las PRs ya estaban mergeadas, GitHub solo permitió publicar las revisiones como *Comment*; la decisión sugerida por la IA figura en el resumen de cada revisión.

| PR | Rol revisado | Archivos revisados | Hallazgos (severidad) | Decisión sugerida por IA | Decisión del revisor humano | Revisión |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| [#69](https://github.com/lucasmengarelli3/SistemaPedidos/pull/69) | Diseñador de Tarjetas CRC | Tarjetas CRC, índices y `ia/a2/disenador-tarjetas-crc.md` | 8 (2 alta, 4 media, 2 baja) | REQUEST CHANGES | 8 aceptados: 3 corregidos en PR #113 y 5 pendientes | [Ver revisión](https://github.com/lucasmengarelli3/SistemaPedidos/pull/69#pullrequestreview-5372196167) |
| [#102](https://github.com/lucasmengarelli3/SistemaPedidos/pull/102) | Modelador de Diagramas de Casos de Uso | `02-diagrama-casos-uso.puml`, índices y `ia/a2/modelador-diagramas-casos-uso.md` | 6 (5 media, 1 baja) | REQUEST CHANGES | 6 aceptados: 1 corregido en PR #120, 2 corregidos parcialmente en PR #109 y 3 pendientes | [Ver revisión](https://github.com/lucasmengarelli3/SistemaPedidos/pull/102#pullrequestreview-5372369414) |
| [#105](https://github.com/lucasmengarelli3/SistemaPedidos/pull/105) | Especialista en Escenarios de Casos de Uso | 12 escenarios, `anexos/introduccion.md` y `ia/a2/especialista-escenarios.md` | 8 (1 alta, 4 media, 3 baja) | REQUEST CHANGES | 8 aceptados y pendientes | [Ver revisión](https://github.com/lucasmengarelli3/SistemaPedidos/pull/105#pullrequestreview-5372422681) |
| [#113](https://github.com/lucasmengarelli3/SistemaPedidos/pull/113) | Diseñador de Tarjetas CRC (corrección de RC1, RC2 y RC3) | Tarjeta `Pedido`, índices de herramientas ágiles y `anexos/introduccion.md` | 5 (3 media, 2 baja) | REQUEST CHANGES | 5 aceptados: 1 corregido en PR #123 y 4 pendientes | [Ver revisión](https://github.com/lucasmengarelli3/SistemaPedidos/pull/113#pullrequestreview-5372492421) |

## Revisiones previas publicadas por el autor de las PRs

Antes de las revisiones anteriores, el mismo prompt se utilizó en revisiones publicadas desde la cuenta de @cmariano93-netizen, que también es autor de las PRs revisadas. Se conservan como antecedente.

| PR | Rol revisado | Archivos revisados | Hallazgos (severidad) | Decisión sugerida por IA | Revisión |
| :--- | :--- | :--- | :--- | :--- | :--- |
| [#69](https://github.com/lucasmengarelli3/SistemaPedidos/pull/69) | Diseñador de Tarjetas CRC | Tarjetas `Producto`, `Pedido` y `Encargado` | 3 (1 alta, 2 media) | REQUEST CHANGES | [Ver revisión](https://github.com/lucasmengarelli3/SistemaPedidos/pull/69#pullrequestreview-5308208137) |
| [#102](https://github.com/lucasmengarelli3/SistemaPedidos/pull/102) | Modelador de Diagramas de Casos de Uso | `02-diagrama-casos-uso.puml` | 3 (1 alta, 2 media) | REQUEST CHANGES | [Ver revisión](https://github.com/lucasmengarelli3/SistemaPedidos/pull/102#pullrequestreview-5308235904) |
| [#102](https://github.com/lucasmengarelli3/SistemaPedidos/pull/102) | Modelador de Diagramas de Casos de Uso (segunda revisión) | `02-diagrama-casos-uso.puml`, `diagramas_de_casos_de_uso.md` | 3 (2 alta, 1 media) | REQUEST CHANGES | [Ver revisión](https://github.com/lucasmengarelli3/SistemaPedidos/pull/102#pullrequestreview-5308291151) |
| [#105](https://github.com/lucasmengarelli3/SistemaPedidos/pull/105) | Especialista en Escenarios de Casos de Uso | Escenarios de cobrar cuenta y entregar pedido | 2 (1 alta, 1 media) | REQUEST CHANGES | [Ver revisión](https://github.com/lucasmengarelli3/SistemaPedidos/pull/105#pullrequestreview-5308456264) |

En las PRs #102 y #105, el Coordinador solicitó cambios en base a esos hallazgos y aprobó la PR una vez aplicadas las correcciones.

## Revisión crítica

- El prompt obliga a usar `anexos/introduccion.md` como criterio de coherencia. Esto permitió detectar inconsistencias entre los entregables y los requisitos, que fueron el tipo de hallazgo predominante en las cuatro revisiones.
- Cada hallazgo generado por la IA se verificó contra los archivos de la PR y el estado actual del repositorio antes de publicarlo. En la decisión del revisor humano se indicó si el hallazgo ya estaba corregido (y en qué PR) o si quedaba pendiente.
- La revisión de la PR #69 cubre también la revisión del Coordinador que faltaba sobre esa PR (RC4).
- Las revisiones se realizaron después del merge de las PRs, por lo que los hallazgos pendientes deben resolverse en ramas `fix/` de cada rol.
- Las revisiones previas referencian `02-diagrama-casos-uso.puml`, que luego se reemplazó por un diagrama por caso de uso.
