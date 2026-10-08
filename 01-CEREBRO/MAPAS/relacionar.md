---
aliases:
  - Relacionar
cssclasses:
  - wide-page
created: 2026-06-25
draft: false
in:
  - "[[Views]]"
related:
  - "[[añadir]]"
  - "[[comunicar]]"
tags:
  - map
title: Relacionar
type: Map
up:
  - "[[Inicio]]"
updated: 2026-06-29
---
# Relacionar

> [!info] Aquí resaltamos las notas que requieren un poco de trabajo
> 
> 1. conocimientos sin conexiones o poco conectados
> 2. conocimientos que "sientes" que necesitan un poco de trabajo

> [!multi-column] 
> > [!orphan]+ # Huérfanos
> > Esta es una vista de las notas in enlaces entrantes ni salientes en `CONOCIMIENTOS` (que, al ser la base del cerebro, nos interesa relacionarla hasta la extenuación).
> > > [!goal] Objetivo: vaciar la lista
> > 
> > > [!important] Un conocimiento sin relaciones es un dato inútil
> > 
> > > [!workflow] Trabajar en estas notas
> > > 1. Piensa en búsquedas que puedan ayudarte a buscar conexiones
> > > 2. Usa `look-for-note-as-keyword.js` para buscar menciones al título o los alias de la nota.
> > 
> > _Mostramos las `10` que más tiempo hace que no se han actualizado (así las vamos rotando sin avasallar por números)._
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
> > Menos de 10 enlaces en total (entrantes + salientes), excluyendo huérfanos.
> > 
> > > [!goal] Objetivo: mantener la lista en mínimos
> > 
> > > [!important] Un conocimiento con pocas relaciones puede indicar huecos de conocimiento que podemos cubrir
> > 
> > > [!workflow] Trabajar en estas notas
> > > 1. Usa la vista de grafo local con una profundidad de 2 o 3 (menos no tiene sentido y más puede dispersar mucho el foco)
> > > 2. Valora si hay conexiones posibles con las notas a 2 o 3 saltos.
> > 
> > _Mostramos las `10` que más tiempo hace que no se han actualizado (así las vamos rotando sin avasallar por números)._
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
> >   AND !contains(file.path, "PERSONAS")
> > SORT file.mday ASC, (length(file.inlinks) + length(file.outlinks)) ASC, file.name ASC
> > LIMIT 10
> > ```
> 
> > [!need-work]+ # Requieren trabajo
> > Notas marcadas con un `status` diferente a `done`. Son notas que pienso (o siento) que requieren un poco más de trabajo.
> > 
> > _Mostramos las `10` que más tiempo hace que no se han actualizado (así las vamos rotando sin avasallar por números)._
> > 
> > ```dataview
> > TABLE WITHOUT ID
> >   file.link AS Nota
> > FROM "01-CEREBRO/CONOCIMIENTOS" AND -#meta
> > WHERE status != "done"
> >   AND !contains(file.path, "PERSONAS")
> > SORT file.mday ASC, file.name ASC
> > LIMIT 10
> > ```
