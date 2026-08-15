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
title: Mapas
type: Map
up:
  - "[[Inicio]]"
updated: 2026-07-13
---
# Mapas

Índice automático de mapas (`in: [[MAPAS]]`).

```dataview
TABLE WITHOUT ID file.link AS Mapa
FROM "01-CEREBRO/MAPAS"
WHERE contains(in, link("MAPAS")) AND !contains(file.name, "Template")
SORT file.name ASC
```
