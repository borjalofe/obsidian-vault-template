---
tags:
  - meta
  - conocimientos
  - conceptos
title: CONCEPTOS
description: Definiciones externas escritas con tus propias palabras.
created: 2026-10-06
updated: 2026-10-06
---

# CONCEPTOS

Definición de algo que no inventaste tú (o sí), redactada por ti. Sirve para fijar lenguaje en el grafo ("latencia", "autorización", "anonimización") sin mezclarlo con tu biografía ni con un procedimiento.

## Problema

Sin conceptos, cada nota reexplica el término o enlaza al vacío. Con conceptos que son ensayos personales, pierdes la frontera con AFIRMACIONES o APRENDIZAJES.

## Alcance

| Incluye | No incluye |
|---------|------------|
| Definiciones externas en tus palabras | "Cómo hago X" (`PROCESOS/`) |
| Ideas de dominio (seguridad, producto, PKM…) | Giros filosóficos tuyos (`APRENDIZAJES/` / `AFIRMACIONES/`) |
| Marca **genérica** (p. ej. identidad visual como disciplina) | Tu marca concreta (`IDENTIDAD/`) |

## Arquitectura

Notas `type: Concept` + hub `CONCEPTOS.md`.

## Ejemplo de nota esperada

Estructura real del vault; cuerpo corto inventado/neutral:

```yaml
---
aliases:
  - anonimización
  - anonymization
  - Anonymization
created: 2026-10-06
draft: false
tags:
  - conceptos
  - conocimientos
title: Anonimización
type: Concept
updated: 2026-10-06
---

# Anonimización

Proceso de eliminar identificadores para impedir la identificación de personas o información sensible.
```

## Cómo ejecutarlo

1. Crear nota en esta carpeta con definición breve.
2. Enlazar desde procesos, publicaciones o accionables con wikilink.
3. No pegar el PDF del temario: el PDF ajeno va a `02-RECURSOS/`; aquí solo tu redacción.

## Decisiones técnicas

| Elegí | Descarté | Por qué |
|-------|----------|---------|
| Tus palabras, origen externo | Copiar párrafos de terceros | Curación + copyright/hábito |
| Separar de APRENDIZAJES | Etiquetar todo como "insight" | Definir no implica cambio de criterio |

## Trade-offs y limitaciones

- **Notas cortas** → parecen pobres; a cambio, se enlazan sin miedo.
- **Solapamiento con ENTIDADES** (p. ej. un estándar) → si es organización, ENTIDADES; si es idea, CONCEPTOS.

## Evidencia de calidad

- Hub local y queries `-#meta`.

## Campos (contrato)

- Típico: `type: Concept`, `title`, `tags` con `conceptos` / `conocimientos`
- Opcional: `aliases`, `status` de forma libre en notas antiguas (no confundir con esfuerzo de ACCIONABLES)

## Lecciones aprendidas

- Una frase precisa gana a un ensayo que nadie vuelve a abrir.
- Si empiezas a hablar de "yo nunca…", saliste de CONCEPTOS.

## Próximos pasos

1. Al escribir un proceso nuevo, extraer términos a conceptos en lugar de redefinirlos inline.
2. Revisar notas largas: partir definición vs opinión.
