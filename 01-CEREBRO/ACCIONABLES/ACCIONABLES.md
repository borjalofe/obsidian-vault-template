---
aliases: []
created: 2026-06-25
draft: false
in:
  - "[[Views]]"
tags:
  - map
  - meta
title: Accionables
type: Map
up:
  - "[[Inicio]]"
updated: 2026-10-05
---
# Accionables

## On

```dataview
TABLE WITHOUT ID
  file.link AS Proyecto,
  rank AS Rank
FROM "01-CEREBRO/ACCIONABLES"
  AND -#meta
WHERE type = "Project"
  AND status = "on"
SORT rank ASC, file.name ASC
```

## Ongoing

```dataview
TABLE WITHOUT ID
  file.link AS Proyecto,
  rank AS Rank
FROM "01-CEREBRO/ACCIONABLES"
  AND -#meta
WHERE type = "Project"
  AND status = "ongoing"
SORT rank ASC, file.name ASC
```

## Sleeping

```dataview
TABLE WITHOUT ID
  file.link AS Proyecto,
  rank AS Rank
FROM "01-CEREBRO/ACCIONABLES"
  AND -#meta
WHERE type = "Project"
  AND status = "sleeping"
SORT rank ASC, file.name ASC
```

## Cancelled / Finished

```dataview
TABLE WITHOUT ID
  file.link AS Proyecto,
  rank AS Rank,
  status AS Status
FROM "01-CEREBRO/ACCIONABLES" OR "01-CEREBRO/PASADO/ACCIONABLES"
  AND -#meta
WHERE type = "Project"
  AND (status = "cancelled" OR status = "finished")
SORT status ASC, rank ASC, file.name ASC
```
