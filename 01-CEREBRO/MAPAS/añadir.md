---
aliases:
  - Añadir
cssclasses:
  - wide-page
created: 2026-07-13
draft: false
in:
  - "[[Views]]"
related:
  - "[[relacionar]]"
  - "[[comunicar]]"
tags:
  - view
title: Añadir
type: View
up:
  - "[[Inicio]]"
updated: 2026-07-13
---
# Añadir

> [!info] Éste es el sitio donde poner todas las notas que captures.
> 
> ¿Quieres capturar un pensamiento fugaz? ¿Una fuente que te ha llamado la atención? ¿Una conversación en alguna red social?
> 
> ¿Y no quieres romper tu foco ahora mismo organizándola?
> 
> ¡Ponlo en `00-ENTRADA/sin-procesar`!

> [!warning] Esto no solo es una bandeja de entrada: es una zona para reposar ideas
> 
> Muchas cosas entran "en caliente" o porque nos "han entrado por los ojos".
> 
> Dales unos días para que se enfríen un poco y puedas ver si son notas que vale la pena integrar.
> 
> Si algo sigue teniendo sentido cuando se ha enfríado, entonces es hora de revisar y priorizar.
> 
> Si no, toca eliminarlo.

> [!activity]+ # Añadidos
> Esta es una vista de las 10 últimas notas añadidas en `00-ENTRADA`.
> 
> > [!goal] Objetivo: vaciar la lista
> 
> > [!important] Ninguna nota debería mantenerse aquí más de 7 días.
> 
> > [!workflow] Trabajar en estas notas
> > 
> > 1. Añade, revisa o modifica contenido
> > 2. Decide dónde va la nota y muévela
> > 3. Elimina la nota si tiene más de 14 días
> 
> ```dataview
> TABLE WITHOUT ID
>   file.link AS "Nota",
>   (date(today) - file.cday).day AS "Tiempo creada",
>   (date(today) - file.mday).day AS "Tiempo sin actualizar"
> FROM "00-ENTRADA/sin-procesar" AND -#meta
> SORT file.cday DESC, file.mday DESC
> LIMIT 10
> ```
