# Plantilla de bóveda Obsidian

Plantilla PKM lista para clonar: taxonomía ENTRADA / CEREBRO / RECURSOS, mapas con Dataview y Folder Notes. Sin Node ni generadores — solo estructura, convenciones de notas y plugins de Obsidian.

## Problema

Abrir Obsidian en una carpeta vacía deja el mismo agujero cada vez: ¿dónde capturo?, ¿dónde vive lo procesado?, ¿qué es un mapa y qué es un archivo muerto? Quería una base opinada que se pueda abrir en cinco minutos sin montar tooling.

## Quién la usa

Alumnos / lectores de formación PKM, y cualquiera que quiera la estructura base antes de saltar a la variante pro.

## Alcance

**Incluye**

- Carpetas `00-ENTRADA`, `01-CEREBRO`, `02-RECURSOS`, `Inicio.md`
- Community plugins recomendados: Dataview + Folder Notes (la bóveda puede traer más ya configurados)
- Semántica de carpetas documentada en los README de cada zona
- Contrato de campos en notas de esfuerzo y editorial: `status` + `rank`, `edit-phase`

**No incluye**

- Scripts, generadores de notas ni capa operativa de IA (eso es [`obsidian-vault-template-pro`](https://github.com/borjalofe/obsidian-vault-template-pro))
- Contenido de curso ni datos personales

## Cómo ejecutarlo

1. Clona o descarga este repositorio.
2. Ábrelo como bóveda en [Obsidian](https://obsidian.md/).
3. Activa **Dataview** y **Folder Notes**.
4. Empieza por [[Inicio]].

## Estructura

| Carpeta | Propósito |
|---------|-----------|
| `00-ENTRADA/` | Captura sin procesar (+ candidatos a medio clasificar) |
| `01-CEREBRO/` | Conocimiento, accionables, agenda, identidad, pasado |
| `02-RECURSOS/` | Archivos de referencia externos |

## Campos (contrato)

- Proyecto/tarea: `status` = `on` → `ongoing` → `sleeping` → `cancelled` / `finished` + `rank` (orden intra-status)
- Editorial: `edit-phase` = `planned` → `outline` → `draft` → `in-progress` → `ready` → `completed`
- No uses `status` para el flujo editorial de una publicación

## Decisiones técnicas

**¿Por qué ENTRADA/CEREBRO/RECURSOS y no PARA o LYT "puro"?**

PARA clasifica proyectos/áreas/recursos/archivos; LYT empuja mapas. Aquí la captura (`00`) queda explícita y el "cerebro" agrupa lo que ya tiene significado (mapas, agenda, accionables). Es una mezcla deliberada, no una copia de un framework.

**¿Por qué Dataview + Folder Notes?**

Bastan para mapas vivos y notas de carpeta. Más plugins en la base = más fricción al clonar.

## Trade-offs y limitaciones

Plantilla **opinada**: si quieres una bóveda mínima de un solo nivel, sobra estructura. Si quieres tooling de generación y briefing, esta repo se queda corta a propósito — usa la pro.

## Evidencia de calidad

Checklist de humo (sin Node):

- [ ] Existen las carpetas `00`–`02` e `Inicio.md`
- [ ] Dataview renderiza las queries de Inicio / mapas
- [ ] Folder Notes abre la nota homónima al entrar en una carpeta

## Lecciones aprendidas

Separar base y pro evita que quien solo quiere carpetas arrastre `package.json`. El precio: dos repos que hay que mantener alineados en semántica de carpetas (la pro regenera esta base vía sync).
