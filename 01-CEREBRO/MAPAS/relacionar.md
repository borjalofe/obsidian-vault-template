---
aliases:
  - Relacionar
cssclasses:
  - wide-page
created: 2026-07-13
draft: false
in:
  - "[[Views]]"
related:
  - "[[añadir]]"
  - "[[comunicar]]"
tags:
  - view
  - conocimientos
title: Relacionar
type: View
up:
  - "[[Inicio]]"
updated: 2026-07-13
---
# Relacionar

> [!info] Aquí resaltamos las notas que requieren un poco de trabajo
> 
> 1. conocimientos sin conexiones o poco conectados
> 2. conocimientos que "sientes" que necesitan un poco de trabajo

> [!multi-column] 
> > [!orphan]+ # Huérfanos
> > Esta es una vista de las notas sin enlaces entrantes ni salientes en `CONOCIMIENTOS`.
> > > [!goal] Objetivo: vaciar la lista
> > 
> > > [!important] Un conocimiento sin relaciones es un dato inútil
> > 
> > > [!workflow] Trabajar en estas notas
> > > 1. Piensa en búsquedas que puedan ayudarte a buscar conexiones
> > > 2. Usa la búsqueda de Obsidian para menciones al título o los alias de la nota
> > 
> > ```dataview
> > TABLE WITHOUT ID
> >    file.link AS Nota,
> >   length(file.inlinks) AS Entrantes,
> >   length(file.outlinks) AS Salientes,
> >   (date(today) - file.cday).day AS "Tiempo creada"
> > FROM "01-CEREBRO/CONOCIMIENTOS" AND -#meta
> > WHERE length(file.inlinks) = 0 AND length(file.outlinks) = 0
> > SORT file.mday ASC, file.name ASC
> > LIMIT 10
> > ```
> 
> > [!lonely]+ # Poco relacionadas
> > Menos de 6 enlaces en total (entrantes + salientes), excluyendo huérfanos.
> > 
> > ```dataview
> > TABLE WITHOUT ID
> >   file.link AS Nota,
> >   length(file.inlinks) AS Entrantes,
> >   length(file.outlinks) AS Salientes,
> >   (length(file.inlinks) + length(file.outlinks)) AS Total
> > FROM "01-CEREBRO/CONOCIMIENTOS" AND -#meta
> > WHERE (length(file.inlinks) + length(file.outlinks)) <= 5
> >   AND (length(file.inlinks) + length(file.outlinks)) > 0
> > SORT file.mday ASC, (length(file.inlinks) + length(file.outlinks)) ASC, file.name ASC
> > LIMIT 10
> > ```
> 
> > [!need-work]+ # Requieren trabajo
> > Notas marcadas con un `status` diferente a `done`.
> > 
> > ```dataview
> > TABLE WITHOUT ID
> >   file.link AS Nota
> > FROM "01-CEREBRO/CONOCIMIENTOS" AND -#meta
> > WHERE status != "done"
> > SORT file.mday ASC, file.name ASC
> > LIMIT 10
> > ```
