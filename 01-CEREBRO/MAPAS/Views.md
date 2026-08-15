---
aliases: []
cssclasses: []
created: 2026-07-13
draft: false
related: []
tags:
  - map
  - meta
title: Views
type: Map
up:
  - "[[Inicio]]"
updated: 2026-07-13
---

# Views

Vistas dinámicas (`in: [[Views]]`).

```dataview
TABLE WITHOUT ID
  file.link AS Vista
FROM -#meta
WHERE contains(in, link("Views")) AND !contains(file.name, "Template")
SORT file.name ASC
```
