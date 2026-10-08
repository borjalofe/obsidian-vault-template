---
tags:
  - meta
  - identidad
  - valores
title: VALORES
description: Palabras o frases comúnmente asociadas a valores (p. ej. honestidad).
created: 2026-10-06
updated: 2026-10-06
---

# VALORES

Etiquetas de valor: palabras o frases cortas que la gente reconoce como valores ("honestidad", "buena fe"). No son tu monólogo de personalidad (eso es AFIRMACIONES).

Se releen junto a AFIRMACIONES cuando anclas criterio.

## Problema

Si solo tienes afirmaciones largas, falta el vocabulario corto para enlazar ética y decisiones. Si todo es valor abstracto sin postura, el criterio no muerde.

## Alcance

| Incluye | No incluye |
|---------|------------|
| Notas `type: Value` con nombre de valor | Posturas en primera persona (`AFIRMACIONES/`) |
| Definición breve de cómo lo entiendes | Procesos operativos |
| Enlaces a afirmaciones/conceptos relacionados | DEC (aunque una DEC pueda citar un valor) |

## Arquitectura

```
VALORES/
├── VALORES.md
└── <Valor>.md
```

## Ejemplo de nota esperada

Estructura alineada a notas reales; texto corto:

```yaml
---
created: 2026-10-06
draft: false
tags:
  - identidad
  - valores
title: Honestidad
type: Value
up:
  - "[[VALORES]]"
updated: 2026-10-06
---

# Honestidad

Decir la verdad aunque incomode.
```

## Cómo ejecutarlo

1. Añade un valor cuando lo uses al juzgar decisiones.

2. Relee los valores junto a afirmaciones cuando decidas.

3. Relaciona con afirmaciones vía `related` (p. ej. un valor sostiene una postura).

## Decisiones técnicas

| Elegí | Descarté | Por qué |
|-------|----------|---------|
| Valor = etiqueta reconocible | Ensayos largos aquí | La prosa larga suele ser afirmación o aprendizaje |
| `type: Value` | Reutilizar Statement | Dataview y cabeza separan capas |

## Trade-offs y limitaciones

- **Lista corta** → mejor; una enciclopedia de virtudes no se usa.
- **Solape cultural** ("buena fe" vs Principio de Hanlon) → enlaza, no dupliques párrafos.

## Evidencia de calidad

- Hub `VALORES.md` con Dataview.

## Campos (contrato)

- `type: Value`
- `up: [[VALORES]]`
- Tags `identidad`, `valores`

## Lecciones aprendidas

- Si la nota empieza por "yo siempre…", casi seguro es AFIRMACIONES.
- Un valor sin uso en decisiones es póster.

## Próximos pasos

1. Mantener el set pequeño y citado desde DEC/afirmaciones.

2. Pedir fricción real: ¿qué valor chocó esta semana?

