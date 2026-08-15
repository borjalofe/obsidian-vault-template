---
aliases: []
created: 2026-07-13
cssclasses: []
draft: false
in:
  - "[[MAPAS]]"
related: []
tags:
  - map
  - meta
  - recursos
title: Recursos
type: Map
up:
  - "[[Inicio]]"
updated: 2026-07-13
---

# Recursos

Colecciones pasivas de `RECURSOS/` vía `in`.

## Todos

```dataview
TABLE WITHOUT ID
  link(file.path, title) AS Fuente,
  type AS Tipo
FROM "01-CEREBRO/RECURSOS"
WHERE file.name != "RECURSOS"
  AND -#meta
SORT title ASC
```
