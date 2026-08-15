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
  - agenda
title: Agenda
type: Map
up:
  - "[[Inicio]]"
updated: 2026-07-13
---
# Agenda

Hub de tiempo activo (`AGENDA`).

## Eventos (hoy y próximos 6 días)

```dataview
TABLE WITHOUT ID
  dateformat(journal-date, "dd/MM/yyyy") AS "Fecha",
  choice(journal-time, journal-time, "—") AS "Hora",
  choice(title, title, "—") AS "Título",
  choice(length(flat(people)) > 0, join(flat(people), " · "), "—") AS "Personas",
  link(file.path, "Más...") AS " "
FROM "01-CEREBRO/AGENDA" AND -#meta
WHERE journal-date
  AND journal-date >= date(today)
  AND journal-date <= date(today) + dur(6 days)
SORT journal-date ASC, choice(journal-time, 1, 0) ASC, journal-time ASC
```
