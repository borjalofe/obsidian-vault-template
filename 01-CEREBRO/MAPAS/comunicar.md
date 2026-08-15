---
aliases:
  - Comunicar
  - Comunicar lo que sé
cssclasses:
  - wide-page
created: 2026-07-13
draft: false
in:
  - "[[Views]]"
related:
  - "[[añadir]]"
  - "[[relacionar]]"
tags:
  - view
title: Comunicar
type: View
up:
  - "[[Inicio]]"
updated: 2026-07-13
---

# Comunicar

> [!goal] # Objetivo(s)
> Comunicar lo que sé como parte del desarrollo de marca: artículos, series, charlas y guías.

> [!abstract] # Descripción
> Publicaciones en subcarpetas bajo `ACCIONABLES/COMUNICAR`. Tras publicar, las notas pasan a `01-CEREBRO/PASADO/REGISTRO/`.

## Calendario editorial

> [!ideas]+ # Ideas
> ```dataview
> TABLE WITHOUT ID
>   link(file.path, title) AS Publicación
> FROM "01-CEREBRO/ACCIONABLES"
> WHERE type = "Publication"
>   AND status = "idea"
> SORT file.mday DESC, title ASC
> LIMIT 10
> ```

## Publicaciones pasadas

```dataview
TABLE WITHOUT ID
  journal-date AS Día,
  link(file.path, title) AS Publicación,
  channel AS Canal
FROM "01-CEREBRO/PASADO/REGISTRO"
WHERE type = "Publication"
  AND journal-date < date(today)
SORT journal-date DESC
LIMIT 20
```
