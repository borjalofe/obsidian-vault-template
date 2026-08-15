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
  - objetivos
title: Objetivos
type: Map
up:
  - "[[IDENTIDAD]]"
updated: 2026-07-13
---
# Objetivos

```dataview
TABLE WITHOUT ID
  link(file.path, title) AS Objetivo
FROM "01-CEREBRO/IDENTIDAD/OBJETIVOS"
WHERE file.name != "OBJETIVOS"
  AND -#meta
SORT title ASC
```
