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
  - identidad
  - afirmaciones
title: Afirmaciones
type: Map
up:
  - "[[IDENTIDAD]]"
updated: 2026-07-13
---

# Afirmaciones

```dataview
TABLE WITHOUT ID
  link(file.path, title) AS Afirmación
FROM "01-CEREBRO/IDENTIDAD/AFIRMACIONES"
WHERE file.name != "AFIRMACIONES"
  AND -#meta
SORT title ASC
```
