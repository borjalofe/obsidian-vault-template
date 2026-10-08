---
tags:
  - meta
  - pasado
  - archivo
title: PASADO
description: Solo archivo de cerrado — accionables terminados y REGISTRO (diario/log).
created: 2026-10-06
updated: 2026-10-06
---

# PASADO

Archivo de lo cerrado. No es un almacén de "cosas viejas sueltas": o es un accionable cerrado, o es registro (trackers/eventos archivados). Las anécdotas cuentan como eventos de agenda ya terminados y viven bajo `REGISTRO/`.

## Problema

Si lo cerrado sigue en AGENDA o ACCIONABLES, Dataview mezcla fuego actual con humo. PASADO saca del camino operativo sin borrar historia.

## Alcance

| Incluye | No incluye |
|---------|------------|
| `ACCIONABLES/` con proyectos `finished` / `cancelled` movidos | Proyectos activos (`01-CEREBRO/ACCIONABLES/`) |
| `REGISTRO/` journals y trackers archivados | Trackers aún abiertos (`AGENDA/`) |
| Eventos/anécdotas ya cerrados (vía REGISTRO) | Recursos externos (`02-RECURSOS/`) |

## Arquitectura

```
PASADO/
├── ACCIONABLES/     # carpetas de proyecto cerradas
└── REGISTRO/        # diario / log (misma jerarquía relativa que AGENDA)
```

```mermaid
flowchart LR
  Acc[ACCIONABLES activos] -->|mover carpeta| AccP[PASADO/ACCIONABLES]

Age[AGENDA]

|archivar tracker| Reg[PASADO/REGISTRO]
-->
```

## Ejemplo de contenido esperado

Proyecto cerrado (la nota de proyecto mantiene contrato; cambia la ubicación):

```yaml
---
status: finished
rank: 99
title: Lab de backups locales
type: Project
---
```

Ruta tras cierre: `PASADO/ACCIONABLES/Lab de backups locales/…`

Detalle de journals: ver [REGISTRO/README.md](REGISTRO/README.md).

## Cómo ejecutarlo

- Accionable: mover carpeta a `PASADO/ACCIONABLES/`.
- Intervalo: mover el tracker desde AGENDA a `PASADO/REGISTRO/` (misma ruta relativa).

No uses PASADO como inbox de "ya no sé dónde ponerlo".

## Decisiones técnicas

| Elegí | Descarté | Por qué |
|-------|----------|---------|
| Dos subcarpetas (accionables vs registro) | Un único dump cronológico | Esfuerzo y diario no se listan igual |

| Mover en lugar de marcar solo | Dejar todo en sitio activo con flag | Dataview del activo deja de verlo |

| Anécdotas = eventos cerrados | Carpeta "historias" | Un solo modelo de tiempo |

## Trade-offs y limitaciones

- **Mover carpetas** → enlaces y hábitos de ruta; a cambio, el activo queda limpio.

- **Archivar con cuidado** → fricción; a cambio, no hay archive fantasma.

## Evidencia de calidad

- Dataview de cancelled/finished en `ACCIONABLES.md` también mira `PASADO/ACCIONABLES`.

## Lecciones aprendidas

- Cerrado ≠ irrelevante: sigue siendo grafo; solo sale del radar operativo.
- Si "pasado" empieza a recibir captura sin curar, has roto el listón: eso es `00-ENTRADA/`.

## Próximos pasos

1. Al cerrar semana, archiva el tracker; no dejar husos en AGENDA.

2. Revisar de vez en cuando `PASADO/ACCIONABLES/` por cierres a medias (`status` aún `ongoing`).
