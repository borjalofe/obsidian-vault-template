---
tags:
  - meta
  - conocimientos
  - personas
title: PERSONAS
description: Fichas de personas físicas (contactos); no organizaciones.
created: 2026-10-06
updated: 2026-10-06
---

# PERSONAS

Personas físicas. Aquí viven las fichas de contacto curadas (`type: People`). Las organizaciones van a `ENTIDADES/`. Los binarios, a `RECURSOS/`.

## Problema

Sin fichas, "hablar con X" en agenda no enlaza a nadie reutilizable. Si metes empresas en PERSONAS, los widgets de cumpleaños se rompen de sentido.

## Alcance

| Incluye | No incluye |
|---------|------------|
| Fichas `type: People` | Personas jurídicas (`ENTIDADES/`) |
| Campos de contacto / prioridad / `in` a mapas | Datos crudos de exports sin curar (`02-RECURSOS/` o entrada) |

| Alta de ficha con frontmatter de grafo | Tareas fechadas (la reunión va a AGENDA con wikilink a la persona) |

## Arquitectura

```
PERSONAS/
├── PERSONAS.md      # hub / widgets
└── <Nombre Apellido>.md
```

## Ejemplo de nota esperada

Campos alineados al vault; **datos inventados** (no uses fichas reales en el README):

```yaml
---
created: 2026-10-06
draft: false
name: Alex
surname: Ejemplo
tags:
  - conocimientos
  - personas
title: Alex Ejemplo
type: People
contact-priority: 5
in:
  - "[[Ejemplo Community]]"
up:
  - "[[PERSONAS]]"
updated: 2026-10-06
---

# Alex Ejemplo

Notas de contexto profesional. Sin emails ni teléfonos en este ejemplo a propósito.
```

## Cómo ejecutarlo

Crea la ficha con `type: People`, `up: [[PERSONAS]]` y `in` hacia mapas/entidades.
Registra interacciones en la ficha o enlazadas; las reuniones fechadas van a AGENDA.

## Decisiones técnicas

| Elegí | Descarté | Por qué |
|-------|----------|---------|
| `type: People` | Reutilizar ENTIDADES | Separación física/jurídica |
| `in` multivalor (mapas, empresas) | Listas solo en el cuerpo | Grafo en frontmatter (`vault-related`) |

| Hub con Dataview | Regenerar listas a mano siempre | El hub se actualiza solo |

## Trade-offs y limitaciones

- **Fichas sensibles** → el vault las tiene; este README no las reproduce.
- **Prioridad de contacto** → hay que mantenerla; si no, los widgets mienten.

## Evidencia de calidad

- Hub PERSONAS con queries (top contactar, cumpleaños) embebidables en `Inicio.md`.

## Campos (contrato)

- `type: People`
- `name` / `surname` (u homólogos)
- `in`, `up`, `related` según grafo
- Opcional: `contact-priority`, `birthdate`, `contacted`

## Lecciones aprendidas

- La reunión es AGENDA; la persona es PERSONAS; el enlace va en `people:` o prosa.
- No dupliques la ficha de la empresa aquí.

## Próximos pasos

1. Altas nuevas copiando el contrato de campos; no inventar frontmatter.

2. Revisar `contact-priority` cuando el widget deje de reflejar la realidad.
