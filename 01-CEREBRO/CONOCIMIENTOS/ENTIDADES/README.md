---
tags:
  - meta
  - conocimientos
  - entidades
title: ENTIDADES
description: Fichas de personas jurídicas (organizaciones, empresas, capítulos, productos como entidad).
created: 2026-10-06
updated: 2026-10-06
---

# ENTIDADES

Personas jurídicas y equivalentes: empresas, capítulos, asociaciones, productos/herramientas tratados como entidad en el grafo. Las personas físicas van a `PERSONAS/`. Los PDFs o imágenes de una compañía van a `01-CEREBRO/RECURSOS/` (p. ej. bajo `compañías/`), no aquí.

## Problema

Si una empresa, una comunidad y un contacto viven en el mismo cajón, los mapas se vuelven imposibles. ENTIDADES fija el sujeto jurídico (o app/org) como ficha.

## Alcance

| Incluye | No incluye |
|---------|------------|
| Empresas, orgs, chapters, apps como entidad | Personas físicas (`PERSONAS/`) |
| Ficha Markdown curada | Adjuntos no-Markdown (`RECURSOS/`) |
| Enlaces a proyectos/eventos vía frontmatter/`related` | Duplicar toda la carpeta del proyecto aquí |

## Arquitectura

```
ENTIDADES/
├── ENTIDADES.md     # MOC / Dataview
└── <Nombre>.md      # ficha
```

## Ejemplo de nota esperada

Anonimizada / herramienta pública como plantilla de campos:

```yaml
---
created: 2026-10-06
draft: false
tags:
  - conocimientos
  - entidades
  - tools
title: Ejemplo Tools S.L.
type: Entity
up:
  - "[[ENTIDADES]]"
updated: 2026-10-06
---

# Ejemplo Tools S.L.

Organización de ejemplo. Relacionar personas y accionables desde sus notas; no copiar organigramas enteros aquí.
```

## Cómo ejecutarlo

1. Crear ficha en esta carpeta.
2. En PERSONAS, enlazar la org vía `in` / `related` según si pertenece o ha pertenecido, o si solo tiene alguna relación.
3. Binarios (logo, contrato PDF) → `RECURSOS/`, no adjuntos masivos en la ficha si puedes evitarlo.

## Decisiones técnicas

| Elegí | Descarté | Por qué |
|-------|----------|---------|

| Jurídicas ≠ físicas | Un solo "contactos" | Mapas asumen PERSONAS para gente |

| Ficha ≠ adjunto | Meter PDFs en ENTIDADES | RECURSOS es el cajón de no-Markdown |

## Trade-offs y limitaciones

- **Mapas temáticos en MAPAS/** pueden agregar entidades sin mover fichas.

## Evidencia de calidad

- `ENTIDADES.md` lista con Dataview y `-#meta`.
- Separación real respecto a `PERSONAS/` en el árbol.

## Lecciones aprendidas

- Un chapter es entidad; la gente del chapter son PERSONAS con `in` hacia mapas/orgs.
- "Compañía" en RECURSOS suele ser carpeta de ficheros, no la ficha jurídica.

## Próximos pasos

1. Enlazar entidades clave desde MAPAS agregados (sin duplicar datos).
