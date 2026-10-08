---
tags:
  - meta
  - cerebro
title: 01-CEREBRO
description: Notas con información curada por ti.
created: 2026-10-06
updated: 2026-10-06
---

# 01-CEREBRO

Notas con información curada por ti. Si aún no lo has pasado por ese filtro, pertenece a `00-ENTRADA/`. Si es material de un tercero sin tu curación, a `02-RECURSOS/`.

## Problema

Mezclar captura, archivos ajenos y notas que ya diste por buenas convierte el vault en un disco duro con wikilinks. El cerebro es el sitio donde confías en lo que hay escrito.

## Alcance

| Incluye | No incluye |
|---------|------------|
| Conocimiento, identidad, accionables, agenda, mapas, pasado, recursos propios | Captura sin curar (`00-ENTRADA/`) |
| Plantillas y no-Markdown que tú generas o curas (`RECURSOS/`) | Temarios y copias de terceros (`02-RECURSOS/`) |

| Contratos de carpeta documentados en README hijos | Inventar carpetas de primer nivel nuevas |

## Arquitectura

```
01-CEREBRO/
├── CONOCIMIENTOS/   # lo que sabes (contenedor)
├── IDENTIDAD/       # lo que eres / te define
├── ACCIONABLES/     # proyectos e intención concreta
├── AGENDA/          # trackers, eventos y tareas con fecha
├── MAPAS/           # agregaciones sin carpeta propia
├── PASADO/          # cerrado (accionables + REGISTRO)
└── RECURSOS/        # plantillas y no-Markdown propios
```

Cada subcarpeta tiene su `README.md` con el contrato local.

## Ejemplo de nota esperada

Cualquier nota aquí debería poder decirse "ya la curé". Ejemplo mínimo (concepto inventado):

```yaml
---
created: 2026-10-06
draft: false
tags:
  - conceptos
  - conocimientos
title: Latencia
type: Concept
updated: 2026-10-06
---

# Latencia

Tiempo que tarda un paquete en ir de A a B. No es lo mismo que [[ancho de banda]].
```

## Cómo ejecutarlo

Empieza por [[Inicio]]. Cada subcarpeta tiene su README con el contrato local.
Promueve desde `00-ENTRADA/` solo cuando la nota ya esté curada.

## Decisiones técnicas

| Elegí | Descarté | Por qué |
|-------|----------|---------|
| Criterio "curado por mí" | Meter aquí todo lo que toco | La confianza del grafo depende de ese listón |

| Subcarpetas por rol (saber / ser / hacer / tiempo) | Una sola carpeta "notas" | Dataview y hábitos asumen rutas estables |

| README por zona | Solo hubs Dataview | El hub lista; el README explica el contrato |

## Trade-offs y limitaciones

- **Curación humana** → más trabajo al promover desde entrada; a cambio, menos basura en queries.

- **Rutas fijas** → menos libertad cosmética; a cambio, los mapas y queries no se rompen.

## Evidencia de calidad

- `Inicio.md` apunta a zonas del cerebro.
- Folder Notes (`ACCIONABLES.md`, `AGENDA.md`, …) viven junto a su carpeta.

## Lecciones aprendidas

- "Lo que sé" y "lo que soy" no comparten el mismo cajón: CONOCIMIENTOS vs IDENTIDAD.
- Lo fechado no compite con lo proyectado: AGENDA vs ACCIONABLES.

## Próximos pasos

1. Mantener READMEs hijos al día cuando cambie un contrato de campos.
2. Seguir promoviendo desde `00-ENTRADA/` con el mismo listón de curación.
