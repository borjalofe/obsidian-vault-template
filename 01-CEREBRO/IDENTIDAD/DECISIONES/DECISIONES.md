---
aliases:
  - Decisiones
created: 2026-10-05
draft: false
tags:
  - map
  - meta
title: Decisiones
type: Map
up:
  - "[[IDENTIDAD]]"
updated: 2026-10-05
---

# Decisiones

DEC personales: `DEC-NNN.md` (contador = max + 1).

DEC de proyecto: en la carpeta del accionable como `DEC-<slug>-NNN.md` (`slug` = carpeta kebab-case ASCII).

Proponer en cooling pad; escribir en el vault tras OK.

```dataview
TABLE WITHOUT ID
  file.link AS DEC,
  status AS Status,
  created AS Created
FROM "01-CEREBRO/IDENTIDAD/DECISIONES"
WHERE type = "Decision"
SORT created DESC
```
