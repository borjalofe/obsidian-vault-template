---
tags:
  - meta
  - conocimientos
  - aprendizajes
title: APRENDIZAJES
description: Notas sobre algo que cambió tu modo de ver, hacer o entender — o tu filosofía.
created: 2026-10-06
updated: 2026-10-06
---

# APRENDIZAJES

Aquí va lo que te cambió el chip: modo de ver, de hacer, de entender, o un trozo de filosofía personal/profesional. No es una definición de diccionario (eso es CONCEPTOS). Tampoco es "hoy aprendí un atajo de teclado" sin consecuencia.

La carpeta puede estar vacía; el listón es alto a propósito.

## Problema

Si todo matiz vago se llama "aprendizaje", la carpeta se llena de ruido y deja de señalar giros reales. Si nunca escribes ninguno, pierdes el rastro de qué te movió.

## Alcance

| Incluye | No incluye |
|---------|------------|
| Cambios de criterio / filosofía con consecuencias | Definiciones externas en tus palabras (`CONCEPTOS/`) |
| Destino típico de candidatos `tipo: aprendizaje` | Procesos paso a paso (`PROCESOS/`) |
| Lecciones que siguen mandando cómo eliges | Eventos fechados (`AGENDA/` / `REGISTRO/`) |

## Arquitectura

Notas planas (o las que necesites) en esta carpeta. Sin subtaxonomía fija por ahora.

## Ejemplo de nota esperada

Inventada; estructura alineada al vault:

```yaml
---
created: 2026-10-06
draft: false
tags:
  - conocimientos
  - aprendizajes
title: El dry-run primero me salvó de archivar la semana equivocada
type: Learning
up:
  - "[[APRENDIZAJES]]"
updated: 2026-10-06
---

# El dry-run primero me salvó de archivar la semana equivocada

Antes empujaba write+archive en el mismo aliento. Ahora el JSON dry-run es el listón: si el intervalo está mal, no toca disco.
```

## Cómo ejecutarlo

1. Candidato en `00-ENTRADA/sin-procesar/candidatos/` con `tipo: aprendizaje`.

2. Desde candidatos de entrada → curar → nota aquí.

3. O escribir directamente cuando ya sepas que el listón se cumple.

## Decisiones técnicas

| Elegí | Descarté | Por qué |
|-------|----------|---------|
| Listón "te cambió el modo" | Diario de micro-tips | Si no cambia criterio, no merece la carpeta |
| Separado de CONCEPTOS | Un solo "conocimiento atómico" | Definir ≠ transformar |

## Trade-offs y limitaciones

- **Carpeta vacía posible** → parece abandono; a cambio, no hay relleno falso.
- **Tipo de frontmatter aún flexible** → menos rigidez; conviene no inventar diez `type` distintos.

## Evidencia de calidad

- Skill de candidatos nombra APRENDIZAJES como destino.
- Esta nota es `#meta` y no ensucia Dataview.

## Lecciones aprendidas

- Un fallo repetido que te cambió el proceso suele ser aprendizaje *y* merecer un PROCESO; puedes tener ambos enlazados.
- Si suena a definición de Wikipedia reescrita, es un CONCEPTO.

## Próximos pasos

1. Promover 1–2 candidatos reales que sí muevan criterio.
2. Cuando exista la primera nota, enlazarla desde el proceso o valor que cambió.
