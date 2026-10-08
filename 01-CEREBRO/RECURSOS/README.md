---
tags:
  - meta
  - recursos
title: RECURSOS
description: Plantillas y no-Markdown generados o curados por ti; la nota de una publicación vive en AGENDA o REGISTRO.
created: 2026-10-06
updated: 2026-10-06
---

# RECURSOS

Material de apoyo **tuyo**: plantillas y ficheros no-Markdown (PDFs, imágenes, exports que curas). Incluye `publicaciones/` con los PDFs de salida.

La nota Markdown de una publicación (con fecha) vive en `AGENDA/` o, ya pasada, en `PASADO/REGISTRO/`. No confundir con `02-RECURSOS/` (material de terceros sin tu curación).

Folder Note / hub: [`RECURSOS.md`](RECURSOS.md) (orientado a colecciones vía `in`; el contrato de carpeta es plantillas + binarios).

## Problema

Si el PDF y el borrador Markdown comparten cajón sin regla, no sabes qué es calendario y qué es artefacto. Si mezclas temarios ajenos aquí, ensucias lo curado con lo externo.

## Alcance

| Incluye | No incluye |
|---------|------------|
| Plantillas (p. ej. slideshow LinkedIn) | Notas Markdown de publicación (AGENDA/REGISTRO) |
| PDFs/imágenes propios (`publicaciones/`, etc.) | Temarios y copias de terceros (`02-RECURSOS/`) |
| Adjuntos de apoyo (p. ej. bajo `compañías/`) | Fichas jurídicas/físicas (`ENTIDADES/` / `PERSONAS/`) |

## Arquitectura

```
RECURSOS/
├── RECURSOS.md
├── plantillas/
├── publicaciones/     # PDFs (y similares), no el Markdown del post
├── compañías/         # adjuntos no-Markdown de apoyo
├── comunidades/
└── eventos/
```

## Ejemplo de contenido esperado

Plantilla (ruta):

```
RECURSOS/plantillas/slideshow para LinkedIn/
```

Publicación: el PDF en `publicaciones/<stem>/…pdf`; la nota fechada, ejemplo mínimo en AGENDA:

```yaml
---
journal-date: 2026-11-06
journal-time: "09:00"
title: BT99 — Ejemplo — ES
type: Publication
---
```

No hace falta (ni conviene) un `.md` de artículo dentro de `RECURSOS/publicaciones/`.

## Cómo ejecutarlo

1. Generas el artefacto (p. ej. skill slideshow) → PDF bajo `publicaciones/`.
2. Programas/fechas la pieza en AGENDA.
3. Al cerrar el tiempo, el Markdown archiva con el flujo de agenda/registro; el PDF se queda aquí.

## Decisiones técnicas

| Elegí | Descarté | Por qué |
|-------|----------|---------|
| PDF aquí, Markdown fechado en agenda | Todo el post en RECURSOS | Tiempo ≠ binario |
| RECURSOS del cerebro ≠ `02-RECURSOS` | Un solo "resources" | Tuyo/curado vs ajeno |
| `compañías/` para adjuntos | Meter PDFs en ENTIDADES | Ficha vs archivo |

## Trade-offs y limitaciones

- **Hub Dataview histórico** en `RECURSOS.md` puede hablar de libros/cursos vía `in`; la norma de carpeta sigue siendo plantillas + no-Markdown. Si una query espera Markdown de "sources", revisa si esa colección sigue viva.
- **`paths.resources` en config apunta a `02-RECURSOS`** — los scripts de "resources" externos no son esta carpeta.

## Evidencia de calidad

- `publicaciones/` con PDFs encaja en la norma no-Markdown.
- Plantillas usadas por skills (slideshow) viven bajo `plantillas/`.

## Lecciones aprendidas

- "Publicaciones" en el nombre de carpeta engaña: aquí está el artefacto, no el calendario editorial.
- Si el fichero lo hizo un tercero y solo lo consultas, es `02`.

## Próximos pasos

1. Mantener `publicaciones/` limpio de Markdown suelto.
2. Nombrar stems de PDF alineados con la nota de AGENDA para encontrarlos sin drama.
