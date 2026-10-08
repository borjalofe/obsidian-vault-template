---
tags:
  - meta
  - identidad
  - decisiones
  - dec
title: DECISIONES
description: Solo decisiones formales (DEC) con contexto, alternativas y consecuencias.
created: 2026-10-06
updated: 2026-10-06
---

# DECISIONES

Solo DEC formales. No es el diario de "hoy decidí cenar pizza". Cada nota sigue la plantilla: contexto, alternativas, decisión, consecuencias.

Las DEC se proponen y se escriben solo tras OK humano (cooling pad / borrador primero).

## Problema

Las decisiones importantes perdidas en chats o journals no se pueden auditar. Decisiones triviales con formato DEC hinchan la carpeta y matan el ritual.

## Alcance

| Incluye | No incluye |
|---------|------------|
| Notas `type: Decision` (DEC-NNN) | Preferencias sueltas sin formato |
| Plantilla `_plantilla-DEC.md` | Objetivos de rumbo (`OBJETIVOS/`) |

| Cooling pad / borradores hasta OK humano | Publicar DEC a medias |

## Arquitectura

```
DECISIONES/
├── DECISIONES.md
├── _plantilla-DEC.md
└── DEC-NNN — título.md
```

## Ejemplo de nota esperada

Según plantilla (contenido inventado):

```yaml
---
created: 2026-10-06
draft: true
status: proposed
tags:
  - meta
title: DEC-001 — dry-run obligatorio antes de archivar semana
type: Decision
updated: 2026-10-06
---

# DEC-001 — dry-run obligatorio antes de archivar semana

## Contexto

Un archive mal apuntado mueve el tracker equivocado a REGISTRO.

## Alternativas

1. Write+archive en un paso
2. Dry-run JSON → OK humano → write/archive

## Decisión propuesta

Opción 2 como norma.

## Consecuencias

Más fricción; menos sorpresas en PASADO.
```

## Cómo ejecutarlo

1. Borrador en cooling pad o nota `draft: true` / `status: proposed`.
2. Tras OK: crear/mover nota aquí con la plantilla.
3. No uses esta carpeta para actas de reunión: eso es AGENDA/REGISTRO.

## Decisiones técnicas

| Elegí | Descarté | Por qué |
|-------|----------|---------|
| Solo DEC formales | Cualquier decisión tipada | El ritual importa si es escaso |

| Sin publicar al primer draft | Firmar DEC sin cooling | Una DEC mal firmada pesa años |

| `status: proposed` en borrador | Publicar como hecho al primer draft | Cooling |

## Trade-offs y limitaciones

- **Pocas DEC** → parece abandono; a cambio, cada una pesa.
- **Numeración DEC-NNN** → hay que cuidarla a mano.

## Evidencia de calidad

- `_plantilla-DEC.md` en la carpeta.

- Plantilla y cooling antes de dar por firme una DEC.

## Campos (contrato)

- `type: Decision`
- `status` de la DEC (p. ej. `proposed` …) — no es el `status` de ACCIONABLES
- Tags; a menudo `meta` en plantilla

## Lecciones aprendidas

- Si no hay alternativas ni consecuencias, no es DEC: es ocurrencia.
- Documentar lo que **no** se decidió (descartes) ahorra reabrir el debate.

## Próximos pasos

1. Numerar la primera DEC real cuando toque un trade-off que vaya a durar.
2. Enlazar DEC relevantes desde procesos o accionables con `related`.
