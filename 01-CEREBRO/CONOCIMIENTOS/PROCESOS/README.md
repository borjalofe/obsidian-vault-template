---
tags:
  - meta
  - conocimientos
  - procesos
title: PROCESOS
description: Cómo haces X de forma reutilizable.
created: 2026-10-06
updated: 2026-10-06
---

# PROCESOS

"Cómo hago X" reutilizable. Si lo puedes seguir dentro de tres meses, encaja aquí. Un desahogo de una tarde no.

## Problema

Sin procesos, cada vez re-inventas el alta de una charla o el review de semana. Con procesos que son actas puntuales, la carpeta se pudre. El listón es reutilización.

## Alcance

| Incluye | No incluye |
|---------|------------|
| Flujos repetibles (`type: Process`) | Definiciones (`CONCEPTOS/`) |

| Base documental de flujos repetibles | Trackers de una semana concreta (`AGENDA/`) |

| Checklists y diagramas de trabajo | Objetivos de rumbo (`OBJETIVOS/`) |

## Arquitectura

```
PROCESOS/
├── PROCESOS.md

├── Alta de charla.md        # ejemplo de flujo operativo
└── …
```

## Ejemplo de nota esperada

Esqueleto (inventado):

```yaml
---
created: 2026-10-06
draft: false
tags:
  - conocimientos
  - procesos
title: Publicar carrusel con dry-run de enlaces
type: Process
up:
  - "[[PROCESOS]]"
updated: 2026-10-06
---

# Publicar carrusel con dry-run de enlaces

1. Borrador en AGENDA con journal-date.
2. Generar PDF a RECURSOS/publicaciones/.
3. Revisar wikilinks rotos antes de programar.
```

## Cómo ejecutarlo

1. Escribe el proceso cuando lo hayas hecho al menos dos veces (o sepas que se repetirá).
2. Candidatos `tipo: proceso` desde entrada → curar → nota aquí.

## Decisiones técnicas

| Elegí | Descarté | Por qué |
|-------|----------|---------|

| Markdown reutilizable aquí | Dejar el procedimiento solo en un chat | La nota es canónica |

| Procesos de sistema en la misma carpeta | Carpeta "meta" aparte | Mismo contrato `Process`; el tag discrimina |

## Trade-offs y limitaciones

- **Procesos de empresa antiguos** → pueden quedar obsoletos; marca fechas en `updated` o archiva prosa.

- **Checklist ≠ acta** → si necesita novela, parte conceptos.

## Evidencia de calidad

- Notas `type: Process` con `up: [[PROCESOS]]`.

- Hub `PROCESOS.md`.

## Campos (contrato)

- `type: Process`
- `up` / `related` según grafo
- Tags `procesos` (+ dominio)

## Lecciones aprendidas

- Si al seguir el proceso inventas pasos que no están en la nota, el proceso está incompleto.

- Un proceso bueno cabe en checklist; si necesita novela, parte conceptos.

## Próximos pasos

1. Cuando un flujo de chat se repita, bajarlo aquí.

2. Revisar procesos Rankia/históricos: dejar claro si siguen vigentes.
