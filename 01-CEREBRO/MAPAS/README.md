---
tags:
  - meta
  - mapas
title: MAPAS
description: Agregaciones tuyas sin carpeta propia; base para generar o seguir algo sin inventar carpeta.
created: 2026-10-06
updated: 2026-10-07
---

# MAPAS

Aquí viven los mapas **sin carpeta asociada**: juntas notas de varios sitios (personas, entidades, accionables, eventos de agenda y registro) sin duplicar datos en una carpeta nueva.

A nivel narrativo hablamos de "mapas" porque ayudan a llegar a las notas. Internamente son el equivalente a una VIEW de SQL. Aún así nos quedamos con la simplicidad narrativa y por eso el nombre de carpeta es MAPAS.

Un Folder Note como `ACCIONABLES.md` **es** un mapa de carpeta, pero se queda dentro de `ACCIONABLES/` por el plugin Folder Note. Si lo movieras aquí, perderías esa potencia.

## Problema

La estructura de carpetas cubre necesidades genéricas (saber, ser, hacer, tiempo). Tus agregaciones ("todo lo de Ejemplo Corp") no deberían obligar a clonar fichas en un árbol paralelo. MAPAS es el sitio de esas agregaciones.

## Para qué (además de "encontrar")

Un mapa no es solo un índice bonito. Es el sitio donde **agregas** de cara a hacer algo con ese material:

| Uso | Ejemplo |
|-----|---------|
| Generar | Publicación, libro, serie LinkedIn, taller, charla: el mapa junta borradores, fuentes, hitos y gente sin meterlos en una carpeta "del libro" |
| Seguir | Elecciones, certificación, candidatura larga, proceso legislativo o normativo: el mapa es el tablero; las fichas y fechas siguen en sus sitios |
| Preparar | Entrevista, demo, onboarding a un cliente/tema: un panorama de lo que ya tienes (CV, proyectos, entidades, eventos) |
| Vigilar un dominio | Seguridad, editorial, un stack: cruza conceptos, proyectos y journals sin clonar el árbol |

Si al cerrar el mapa no te queda claro *para qué* lo abres la próxima vez, probablemente no hacía falta.

## Alcance

| Incluye | No incluye |
|---------|------------|
| Mapas temáticos transversales (`seguridad.md`, etc.) | Sustituir la taxonomía de carpetas |
| Agregaciones para generar o hacer seguimiento (pub, libro, elecciones…) | Proyecto con intención y status (`ACCIONABLES/`) |
| Dataview / índices por `in: [[MAPAS]]` u homólogo | Folder Notes de carpeta (viven en su carpeta) |
| Hubs que cruzan zonas del cerebro | Copiar notas enteras "para tenerlas juntas" |

## Arquitectura

```
MAPAS/
├── MAPAS.md           # índice
├── seguridad.md
├── comunicar.md
└── …
```

```mermaid
flowchart TB
  subgraph carpetas [Carpetas genéricas]
    P[PERSONAS]
    E[ENTIDADES]
    A[ACCIONABLES]
    T[TIEMPO (AGENDA o REGISTRO)]
  end
  M[Mapa en MAPAS] --> P
  M --> E
  M --> A
  M --> T
```

## Ejemplo de nota esperada

Mapa agregado inventado (sin datos privados):

```yaml
---
created: 2026-10-06
draft: false
in:
  - "[[MAPAS]]"
tags:
  - map
  - meta
title: Ejemplo Corp — panorama
updated: 2026-10-06
---

# Ejemplo Corp — panorama

Agrega sin mover fichas:

- Entidad: [[Ejemplo Tools S.L.]]
- Personas: enlaces vía Dataview o wikilinks
- Accionables y eventos: `related` / queries por proyecto o tag

No copies aquí el CV de nadie ni el PDF del contrato.
```

Hub de la carpeta (`MAPAS.md`) lista notas con `in` hacia MAPAS.

## Cómo ejecutarlo

1. Crea el mapa cuando necesites una agregación que no merece carpeta nueva (sobre todo si vas a generar o seguir algo con ese material).
2. Pon `in: [[MAPAS]]` (o el enlace que use tu Dataview).
3. Deja los Folder Notes de carpeta donde están.

## Decisiones técnicas

| Elegí | Descarté | Por qué |
|-------|----------|---------|
| Mapas transversales aquí | Duplicar árboles por cliente/tema | Un solo grafo; muchas lecturas |
| Folder Note en carpeta origen | Centralizar todos los mapas en MAPAS/ | UX del plugin + queries locales |
| Narrativa "mapas" | Renombrar la carpeta a VISTAS | Menos fricción al hablar del vault |

## Trade-offs y limitaciones

- **Dos sitios con "mapas"** (MAPAS/ vs Folder Note) → hay que explicar el corte; a cambio, cada uno gana en su sitio.
- **Mapas desactualizados** → Dataview mitiga; la prosa manual envejece.

## Evidencia de calidad

- `MAPAS.md` con query por `in`.
- `paths.maps` → esta carpeta.
- Folder Notes activos fuera de aquí (`ACCIONABLES.md`, `AGENDA.md`, …).

## Lecciones aprendidas

- Si estás a punto de crear `ACCIONABLES/EjemploCorp/` solo para agrupar, para y prueba un mapa.
- Carpetas = genérico; mapas = tus agregaciones.
- Si el mapa es la mesa de trabajo de un libro o de unas elecciones, el entregable o el evento siguen en AGENDA/ACCIONABLES; aquí solo el panorama.

## Próximos pasos

1. Un mapa por agregación que de verdad uses, no por si acaso.
2. Preferir Dataview/`related` a pegar listas que ya son frontmatter en otro sitio.
