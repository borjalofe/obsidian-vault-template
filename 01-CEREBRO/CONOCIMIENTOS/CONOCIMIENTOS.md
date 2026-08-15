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
  - conocimientos
title: Conocimientos
type: Map
up:
  - "[[Inicio]]"
updated: 2026-07-13
---
# Conocimientos

```dataview
TABLE WITHOUT ID
  link(file.path, title) AS Conocimiento
FROM "01-CEREBRO/CONOCIMIENTOS"
WHERE file.name != "CONOCIMIENTOS"
  AND -#meta
SORT title ASC
```
