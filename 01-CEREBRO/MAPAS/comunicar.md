---
aliases:
  - Comunicar
  - Comunicar lo que sé
created: 2026-06-28
cssclasses:
  - wide-page
draft: false
in:
  - "[[Views]]"
related:
  - "[[añadir]]"
  - "[[relacionar]]"
tags:
  - map
title: Comunicar
type: Map
up:
  - "[[Inicio]]"
updated: 2026-06-29
---

# Comunicar

> [!goal] # Objetivo(s)
> Comunicar lo que sé como parte del desarrollo de marca: artículos, series, charlas y guías.

> [!abstract] # Descripción
> Publicaciones en subcarpetas bajo [[COMUNICAR]]. Tras publicar, las notas pasan a `01-CEREBRO/PASADO/REGISTRO/`.

## Calendario editorial

> [!multi-column]
> > [!ideas]+ # Ideas
> > 
> > _Mostramos las `10` ideas actualizadas más recientemente_
> > 
> > ```dataview
> > TABLE WITHOUT ID
> >   link(file.path, title) AS Publicación
> > FROM "01-CEREBRO/ACCIONABLES"
> > WHERE type = "Publication"
> >   AND status = "idea"
> > SORT file.mday DESC, title ASC
> > LIMIT 10
> > ```
> 
> > [!planned]+ # Planeados
> > ```dataview
> > TABLE WITHOUT ID
> >   journal-date AS Previsto,
> >   link(file.path, title) AS Publicación,
> >   channel AS Canal,
> >   series AS Serie
> > FROM "01-CEREBRO/ACCIONABLES"
> > WHERE type = "Publication"
> >   AND status = "planned"
> > SORT journal-date ASC
> > ```
> 
> > [!wip]+ # En curso
> > ```dataview
> > TABLE WITHOUT ID
> >   journal-date AS Previsto,
> >   link(file.path, title) AS Publicación,
> >   channel AS Canal,
> >   series AS Serie
> > FROM "01-CEREBRO/ACCIONABLES"
> > WHERE type = "Publication"
> >   AND status = "in-progress"
> > SORT journal-date ASC
> > ```
> 
> > [!scheduled]- # Programados
> > ```dataview
> > TABLE WITHOUT ID
> >   journal-date AS Día,
> >   journal-time AS Hora,
> >   link(file.path, title) AS Publicación,
> >   channel AS Canal,
> >   series AS Serie
> > FROM "01-CEREBRO/PASADO/REGISTRO"
> > WHERE type = "Publication"
> >   AND journal-date >= date(today)
> > SORT journal-date DESC, journal-time DESC
> > ```

## Ideas

> [!ideas]- # Backlog
> ```dataview
> TABLE WITHOUT ID
>   link(file.path, title) AS Publicación
> FROM "01-CEREBRO/ACCIONABLES"
> WHERE type = "Publication"
>   AND status = "idea"
> SORT title ASC
> ```

## Publicaciones pasadas

> [!multi-column]
> > [!done]- # Recientes
> > ```dataview
> > TABLE WITHOUT ID
> >   journal-date AS Día,
> >   journal-time AS Hora,
> >   link(file.path, title) AS Publicación,
> >   channel AS Canal,
> >   series AS Serie
> > FROM "01-CEREBRO/PASADO/REGISTRO"
> > WHERE type = "Publication"
> >   AND journal-date < date(today)
> >   AND journal-date > date(today) - dur(15 days)
> > SORT journal-date DESC, journal-time DESC
> > ```
> 
> > [!done]- # Publicados
> > ```dataview
> > TABLE WITHOUT ID
> >   journal-date AS Día,
> >   journal-time AS Hora,
> >   link(file.path, title) AS Publicación,
> >   channel AS Canal,
> >   series AS Serie
> > FROM "01-CEREBRO/PASADO/REGISTRO"
> > WHERE type = "Publication"
> >   AND journal-date < date(today)
> > SORT journal-date DESC, journal-time DESC
> > ```
