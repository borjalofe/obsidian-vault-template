---
aliases: []
created: 2026-06-18
draft: false
in:
  - "[[Views]]"
tags:
  - map
  - meta
title: Recursos
type: Map
updated: 2026-06-18
---

# Recursos

Colecciones pasivas de `RECURSOS/` vía `in`.

## Libros

```dataview
TABLE WITHOUT ID
  file.link AS Libro,
  author AS Autor
FROM "01-CEREBRO/RECURSOS" AND -#meta
WHERE in AND contains(in, link("Books"))
SORT file.name ASC
```

## Cursos

```dataview
TABLE WITHOUT ID
  file.link AS Curso
FROM "01-CEREBRO/RECURSOS" AND -#meta
WHERE in AND contains(in, link("Courses"))
SORT file.name ASC
```

## Todos

```dataview
TABLE WITHOUT ID
  file.link AS Fuente,
  type AS Tipo
FROM "01-CEREBRO/RECURSOS" AND -#meta
WHERE in AND contains(in, link("Sources"))
SORT file.name ASC
```
