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
  - identidad
title: Identidad
type: Map
up:
  - "[[Inicio]]"
updated: 2026-07-13
---
# Identidad

```dataview
TABLE WITHOUT ID
  link(file.path, title) AS Nota
FROM "01-CEREBRO/IDENTIDAD"
WHERE file.name != "IDENTIDAD"
  AND -#meta
SORT title ASC
```
