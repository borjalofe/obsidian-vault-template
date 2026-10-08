---
aliases: []
created: 2026-06-18
draft: false
in:
  - "[[MAPAS]]"
tags:
  - map
  - meta
title: Mapas
type: Map
up:
  - "[[Inicio]]"
updated: 2026-09-16
---
# Mapas

Índice automático de mapas (`in: [[MAPAS]]`).

```dataview
TABLE WITHOUT ID file.link AS Mapa
WHERE contains(in, link("MAPAS")) AND !contains(file.name, "Template") AND -#meta
SORT file.name ASC
```
