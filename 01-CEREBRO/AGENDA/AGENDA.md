---
aliases: []
created: 2026-06-25
draft: false
in:
  - "[[Views]]"
tags:
  - map
  - meta
title: Agenda
type: Map
up:
  - "[[Inicio]]"
updated: 2026-06-25
---
# Agenda

Hub de tiempo activo (`AGENDA`).

Las secciones siguientes pueden embeberse como "widgets".

## Eventos (en los próximos 7 días)

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
