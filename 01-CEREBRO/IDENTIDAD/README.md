---
tags:
  - meta
  - identidad
title: IDENTIDAD
description: Lo que eres o te define — marca propia, CV, valores, afirmaciones, DEC, objetivos.
created: 2026-10-06
updated: 2026-10-06
---

# IDENTIDAD

Lo que eres (o te define): marca propia, CV, valores, afirmaciones, decisiones formales y objetivos de rumbo. Lo que **sabes** en genérico vive en `CONOCIMIENTOS/`. Un concepto de "identidad visual" como disciplina → conocimientos; el sistema visual de **tu** marca → aquí (p. ej. `BRAND.md`).

## Problema

Mezclar "soy" con "sé" hace que valores/afirmaciones y un glosario técnico peleen el mismo oxígeno. IDENTIDAD es el sitio del criterio personal y la representación pública tuya.

## Alcance

| Incluye | No incluye |
|---------|------------|
| `BRAND`, CV, perfiles | Conceptos genéricos de dominio |
| `VALORES/`, `AFIRMACIONES/`, `DECISIONES/`, `OBJETIVOS/` | Proyectos (`ACCIONABLES/`) |
| Material que define quién/cómo eres | Temarios de terceros (`02-RECURSOS/`) |

## Arquitectura

```
IDENTIDAD/
├── BRAND.md
├── CV.md
├── AFIRMACIONES/
├── DECISIONES/
├── OBJETIVOS/
└── VALORES/
```

## Ejemplo de nota esperada

En la raíz, piezas de marca/CV (no se reproducen datos sensibles aquí). Subcarpetas: ver sus README. Corte rápido:

```markdown
<!-- CONOCIMIENTOS/CONCEPTOS: -->
Identidad visual — disciplina de diseño…

<!-- IDENTIDAD: -->
BRAND — cómo se presenta *mi* marca en canales…
```

## Cómo ejecutarlo

Relee VALORES + AFIRMACIONES cuando necesites anclar criterio.
Las DEC formales viven en `DECISIONES/` (plantilla; sin publicar borradores a medias).
Editar BRAND/CV a mano o con el flujo editorial del proyecto que toque; no mezclar con CONCEPTOS.

## Decisiones técnicas

| Elegí | Descarté | Por qué |
|-------|----------|---------|

| Saber vs ser | Un solo "personal" | Identidad y glosario no son lo mismo |

| DEC solo formales en subcarpeta | Cualquier decisión en un journal | Trazabilidad de decisiones gordas |
| OBJETIVOS sin fecha aquí | Meter rumbo en AGENDA | Agenda exige fecha |

## Trade-offs y limitaciones

- **BRAND/CV grandes** → pesan en el vault; a cambio, una sola fuente para adaptar ofertas.
- **Frontera con conceptos de marca** → a veces dudosa; pregunta: ¿habla de mí o del oficio?

## Evidencia de calidad

- VALORES + AFIRMACIONES + DECISIONES + OBJETIVOS viven bajo esta carpeta.

## Lecciones aprendidas

- Si la nota podría firmarla cualquier diseñador sin cambiar nombres, probablemente es CONCEPTOS.
- Si cambia cómo te presentas o decides, es IDENTIDAD.

## Próximos pasos

1. Mantener OBJETIVOS vivos aunque la carpeta empiece vacía: el rumbo escrito manda sobre el ruido semanal.
2. DEC con plantilla; no colar "decidí X" suelto sin número/contexto.
