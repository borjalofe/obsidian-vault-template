---
tags:
  - meta
  - identidad
  - afirmaciones
title: AFIRMACIONES
description: Cosas que dices de ti mismo como base de personalidad.
created: 2026-10-06
updated: 2026-10-06
---

# AFIRMACIONES

Frases que dices de ti como base de personalidad o criterio operativo personal. No son el nombre de un valor ("honestidad"); son tu postura ("no doy el primer golpe, pero me aseguro de dar el último").

Se releen junto a VALORES cuando anclas criterio.

## Problema

Sin afirmaciones, el ancla queda en palabras abstractas. Sin separarlas de VALORES, todo es eslogan y nada es postura.

## Alcance

| Incluye | No incluye |
|---------|------------|
| Posturas en primera persona / criterio propio | Etiquetas de valor (`VALORES/`) |
| Notas `type: Statement` | DEC formales (`DECISIONES/`) |
| Enlaces a valores/conceptos que las sostienen | Tareas o proyectos |

## Arquitectura

```
AFIRMACIONES/
├── AFIRMACIONES.md    # Dataview
└── <afirmación>.md
```

## Ejemplo de nota esperada

Estructura real; texto inventado (no copies afirmaciones privadas al documentar fuera):

```yaml
---
created: 2026-10-06
draft: false
tags:
  - afirmaciones
  - identidad
title: primero arreglo el contrato luego el código
type: Statement
up:
  - "[[AFIRMACIONES]]"
updated: 2026-10-06
---

# primero arreglo el contrato luego el código

Si el acuerdo es borroso, programar más no lo arregla. Bajo a tierra el "qué es hecho" antes de abrir el editor.
```

## Cómo ejecutarlo

1. Escribe la afirmación cuando la uses de verdad al decidir.

2. Relee afirmaciones junto a VALORES cuando decidas.

3. Enlaza con `related` a valores o conceptos; no listes "ver también" en el cuerpo.

## Decisiones técnicas

| Elegí | Descarté | Por qué |
|-------|----------|---------|
| Postura ≠ etiqueta de valor | Un solo "principios" | Criterio necesita ambas capas |
| Título = la frase (a menudo minúsculas) | Títulos bonitos de marketing | La nota *es* la frase |

## Trade-offs y limitaciones

- **Títulos largos** → feos en el explorador; a cambio, buscas la frase tal cual.
- **Solape con APRENDIZAJES** → si narra un giro pasado, puede vivir allí; si manda el presente, aquí.

## Evidencia de calidad

- Hub Dataview en `AFIRMACIONES.md`.

## Campos (contrato)

- `type: Statement` (cuando esté tipada)
- `up: [[AFIRMACIONES]]`
- Tags `afirmaciones`, `identidad`

## Lecciones aprendidas

- Una afirmación que no usas al decidir es decoración.
- Si cabe en una palabra de valor, probablemente es VALORES.

## Próximos pasos

1. Contrastar afirmaciones con lo que pediste esa semana.

2. Retirar o reescribir las que ya no firmas.
