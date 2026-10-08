---
tags:
  - meta
  - recursos
  - externos
title: 02-RECURSOS
description: Recursos externos no creados ni curados por ti; copia para consultar.
created: 2026-10-06
updated: 2026-10-06
---

# 02-RECURSOS

Material de terceros: no lo creaste tú ni lo curaste como nota del cerebro. Lo guardas para consultarlo (temarios, PDFs de curso, exports). Si lo reescribes con tus palabras, el resultado curado va a `01-CEREBRO/`.

## Problema

Meter el PDF del temario de un curso junto a tus conceptos hace que Dataview trate basura ajena como conocimiento tuyo. Esta carpeta marca el límite: "tengo copia", no "esto es mío".

## Alcance

| Incluye | No incluye |
|---------|------------|
| Temarios, apuntes y materiales de terceros | Notas curadas (`01-CEREBRO/`) |
| Exports y dumps de referencia (p. ej. CSV) | Plantillas y PDFs que **tú** generas (`01-CEREBRO/RECURSOS/`) |

## Arquitectura

```
02-RECURSOS/
├── subcarpeta-1/
├── subcarpeta-2/
└── subcarpeta-3/
```

## Ejemplo de contenido esperado

No hace falta Markdown canónico. Un temario de tercero podría encajar así:

```
02-RECURSOS/ESTUDIOS/Curso-Ejemplo-Tercero/
├── modulo-01.pdf
└── syllabus.md        # si viene del curso; no es tu nota curada
```

Si de ese temario sacas una definición en tus palabras → `01-CEREBRO/CONOCIMIENTOS/CONCEPTOS/`.
Si te cambia cómo trabajas → `01-CEREBRO/CONOCIMIENTOS/APRENDIZAJES/`.
Si realizas acciones a raíz de ello → `01-CEREBRO/AGENDA/` → `01-CEREBRO/PASADO/REGISTRO/`.

## Cómo ejecutarlo

1. Copia el material bajo una subcarpeta clara.
2. No lo "promuevas" al cerebro sin reescribir/curar.

## Decisiones técnicas

| Elegí | Descarté | Por qué |
|-------|----------|---------|
| Capa `02` separada del cerebro | Meter externos en `01-CEREBRO/RECURSOS/` | RECURSOS del cerebro es tuyo (plantillas, PDFs propios) |
| Sin obligación de frontmatter | Forzar `type: Concept` en PDFs ajenos | No es nota curada |

## Trade-offs y limitaciones

- **Copia local de terceros** → ocupa disco y puede quedar desactualizada; a cambio, consultable offline.

- **Externos aquí** → el material propio de plantillas/PDFs está en `01-CEREBRO/RECURSOS/`.

## Evidencia de calidad

- El material propio (plantillas, PDFs generados) vive en `01-CEREBRO/RECURSOS/`, no aquí.

## Lecciones aprendidas

- "Tener el PDF" no es lo mismo que "haberlo curado".
- Si empiezas a anotar encima del temario con criterio propio, esa nota nueva ya no es `02`; es cerebro.

## Próximos pasos

1. Nombrar subcarpetas de estudio por curso/origen, no por mood.
2. Cuando un extracto se vuelva definición tuya, crear concepto/aprendizaje y dejar el original aquí.
