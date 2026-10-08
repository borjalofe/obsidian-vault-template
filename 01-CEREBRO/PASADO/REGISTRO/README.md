---
tags:
  - meta
  - registro
  - diario
  - pasado
title: REGISTRO
description: Journals, trackers archivados (Weekly/Quarterly/Yearly) y milestones; diario/log del vault.
created: 2026-10-06
updated: 2026-10-07
---

# REGISTRO

Diario / log: trackers ya archivados desde AGENDA (`Weekly` / `Quarterly` / `Yearly`), eventos pasados (`Anecdote` / `Journal` / `Publication`) e hitos (`Milestone`). Misma jerarquía relativa que la agenda activa.

## Problema

Sin registro, la revisión de Q o de año inventa el pasado. Con registro mezclado en AGENDA, el futuro no se lee.

## Alcance

| Incluye | No incluye |
|---------|------------|
| Trackers archivados (`Weekly` / `Quarterly` / `Yearly`) | Trackers abiertos (`AGENDA/`) |
| Eventos y publicaciones ya pasadas | Proyectos cerrados (`PASADO/ACCIONABLES/`) |
| `Milestone` con `year` + `quarter` | Captura sin curar |

## Arquitectura

```
REGISTRO/
├── 2026/
│   ├── weeklies/2026-Www - Tareas semanales.md
│   ├── qs/2026-Qn.md
│   └── MM/YYYY-MM-DD….md    # Anecdote / Journal / Publication / Milestone
└── …
```

Al archivar, el `type` del tracker **no** cambia.

Los Dataview de Índice en Yearly/Quarterly miran AGENDA **y** REGISTRO para listar semanas e hijos ya cerrados.

## Ejemplo de nota esperada

Tracker archivado (Weekly):

```yaml
---
aliases:
  - 2026-W39
journal-date: 2026-09-27
journal-start-date: 2026-09-21
journal-end-date: 2026-09-27
title: 2026-W39 — Tareas semanales
type: Weekly
year: 2026
quarter: Q3
up:
  - "[[2026-Q3]]"
---
```

Yearly archivado (mismo contrato que AGENDA; el `type` no cambia):

```yaml
---
aliases:
  - "2026"
  - plan 2026
  - plan operativo 2026
journal: Anual
journal-date: 2026-01-01
journal-start-date: 2026-01-01
journal-end-date: 2026-12-31
title: Plan operativo 2026
type: Yearly
year: 2026
---
```

Hito:

```yaml
---
journal-date: 2026-10-06
title: Ejemplo de hito
type: Milestone
year: 2026
quarter: Q4
---
```

## Cómo ejecutarlo

Archiva trackers cerrados desde AGENDA moviendo el fichero aquí (misma ruta relativa).
Eventos pasados (`Anecdote` / `Journal` / `Publication`) y `Milestone` también viven bajo esta jerarquía.

## Decisiones técnicas

| Elegí | Descarté | Por qué |
|-------|----------|---------|

| Misma ruta relativa AGENDA ↔ REGISTRO | Renombrar al archivar | Rutas y Dataview estables |

| `Milestone` etiquetado con `year`/`quarter` | Solo filtrar por fechas | Dataview en Yearly/Q simples |
| Sin tracker diario aquí | Journal paralelo al id del intervalo como cierre | Un artefacto por intervalo |

## Trade-offs y limitaciones

- **Años antiguos en el árbol** → ruido al navegar; grafo completo a cambio.

- **Archive tras review** → el cierre y el movimiento van juntos.

## Evidencia de calidad

- Archivado = movido; `Weekly` sigue `Weekly` (el `type` no cambia).

## Campos (contrato)

- Hereda el contrato de AGENDA para trackers y eventos.
- `Milestone`: `journal-date`, `year`, `quarter` (`Qn` por mes de la fecha).

## Lecciones aprendidas

- Si necesitas el relato de una semana, ábrela aquí; no la reconstruyas desde el chat.
- Publicación pasada: Markdown en el log; PDF en `RECURSOS/publicaciones/`.

## Próximos pasos

1. Cerrar W en curso con review y mover a REGISTRO.

2. Altas de hitos con `year`/`quarter` desde el día uno.
