---
tags:
  - meta
  - conocimientos
title: CONOCIMIENTOS
description: Contenedor de lo que sabes — conceptos, aprendizajes, entidades, personas, procesos.
created: 2026-10-06
updated: 2026-10-06
---

# CONOCIMIENTOS

Contenedor. Aquí no hay criterio propio más allá de agrupar lo que **sabes**. Lo que **eres** va a `IDENTIDAD/`.

## Problema

Sin este cajón, personas, procesos y definiciones compiten con proyectos y con la marca personal en el mismo sitio. El contenedor fija el corte: conocimiento reutilizable, no rumbo ni calendario.

## Alcance

| Incluye | No incluye |
|---------|------------|
| Subcarpetas de saber (ver arquitectura) | Identidad, valores, DEC, objetivos |
| Destino de candidatos tipo aprendizaje/proceso | Captura sin curar (`00-ENTRADA/`) |
| Fichas de personas físicas y jurídicas | Binarios/plantillas (`RECURSOS/`) |

## Arquitectura

```
CONOCIMIENTOS/
├── APRENDIZAJES/   # te cambió el modo de ver/hacer
├── CONCEPTOS/      # definición externa en tus palabras
├── ENTIDADES/      # personas jurídicas
├── PERSONAS/       # personas físicas
└── PROCESOS/       # cómo hago X (reutilizable)
```

Cada hija tiene README con ejemplo.

## Ejemplo de nota esperada

No suele haber notas sueltas en la raíz de CONOCIMIENTOS; el ejemplo vive en una hija. Concepto mínimo:

```yaml
---
title: Latencia
type: Concept
tags:
  - conceptos
  - conocimientos
---

# Latencia

Definición en tus palabras de una idea que no inventaste tú.
```

## Cómo ejecutarlo

- Crear la nota en la subcarpeta que toque (PERSONAS, CONCEPTOS, PROCESOS, APRENDIZAJES, ENTIDADES).
- Candidatos desde `00-ENTRADA/sin-procesar/candidatos/` → promover tras curar.

## Decisiones técnicas

| Elegí | Descarté | Por qué |
|-------|----------|---------|
| Contenedor sin notas "hub" obligatorias en raíz | Forzar un mapa único aquí | Cada hija tiene su mapa/Folder Note |
| Saber vs ser (CONOCIMIENTOS vs IDENTIDAD) | Todo "notas personales" juntas | Una definición de marca genérica no es tu marca |

## Trade-offs y limitaciones

- **Solo contenedor** → poco que leer en esta carpeta; la sustancia está un nivel abajo.
- **Frontera con IDENTIDAD** → a veces duele decidir; la regla es genérico/sé vs mío/soy.

## Evidencia de calidad

- `paths.knowledge` → `01-CEREBRO/CONOCIMIENTOS`.
- `paths.contacts` → `…/PERSONAS`.

## Lecciones aprendidas

- Si la nota habla de "quién soy", mal carpeta.
- Si es el PDF del curso de otro, mal capa: eso es `02-RECURSOS/`.

## Próximos pasos

1. Ir llenando APRENDIZAJES cuando un candidato merezca el listón.
2. No crear más subtipos en la raíz sin necesidad real.
