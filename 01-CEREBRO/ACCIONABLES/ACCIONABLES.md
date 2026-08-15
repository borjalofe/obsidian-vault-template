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
  - accionables
title: Accionables
type: Map
up:
  - "[[Inicio]]"
updated: 2026-07-13
---
# Accionables

## 💡 Ideas

```dataview
TABLE WITHOUT ID
  file.link AS Proyecto,
  rank AS Rank
FROM "01-CEREBRO/ACCIONABLES"
  AND -#meta
WHERE type = "Project"
  AND status = "idea"
SORT rank ASC, file.name ASC
```

## ♻️ Planeados

```dataview
TABLE WITHOUT ID
  file.link AS Proyecto,
  rank AS Rank
FROM "01-CEREBRO/ACCIONABLES"
  AND -#meta
WHERE type = "Project"
  AND status = "planned"
SORT rank ASC, file.name ASC
```

## 🔥 En curso

```dataview
TABLE WITHOUT ID
  file.link AS Proyecto,
  rank AS Rank
FROM "01-CEREBRO/ACCIONABLES"
  AND -#meta
WHERE type = "Project"
  AND status = "in-progress"
SORT rank ASC, file.name ASC
```
