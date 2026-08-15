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
  - valores
title: Valores
type: Map
up:
  - "[[IDENTIDAD]]"
updated: 2026-07-13
---

# Valores

```dataview
TABLE WITHOUT ID
  link(file.path, title) AS Valor
FROM "01-CEREBRO/IDENTIDAD/VALORES"
WHERE file.name != "VALORES"
  AND -#meta
SORT title ASC
```
