# Plantilla de bóveda Obsidian

Plantilla PKM lista para clonar: taxonomía ENTRADA / CEREBRO / RECURSOS, mapas con Dataview y Folder Notes. Sin Node, sin Plop — solo estructura y plugins mínimos.

## Problema

Abrir Obsidian en una carpeta vacía deja el mismo agujero cada vez: ¿dónde capturo?, ¿dónde vive lo procesado?, ¿qué es un mapa y qué es un archivo muerto? Quería una base opinada que un alumno o yo mismo pudiera abrir en cinco minutos sin montar tooling.

## Quién la usa

Alumnos / lectores de formación PKM, y cualquiera que quiera la estructura base antes de saltar a la variante pro.

## Alcance

**Incluye**

- Carpetas `00-ENTRADA` … `04-GENAI`, `Inicio.md`
- Community plugins recomendados: Dataview + Folder Notes
- Semántica de carpetas documentada en los README de cada zona

**No incluye**

- Automatización Plop, perfiles JSON ni scripts Node (eso es [`obsidian-vault-template-pro`](https://github.com/borjalofe/obsidian-vault-template-pro))
- Contenido de curso ni datos personales

## Cómo ejecutarlo

1. Clona o descarga este repositorio.
2. Ábrelo como bóveda en [Obsidian](https://obsidian.md/).
3. Activa **Dataview** y **Folder Notes**.
4. Empieza por [[Inicio]].

## Estructura

| Carpeta | Propósito |
|---------|-----------|
| `00-ENTRADA/` | Captura sin procesar |
| `01-CEREBRO/` | Conocimiento, accionables, agenda, identidad |
| `02-RECURSOS/` | Archivos de referencia externos |
| `03-AUTOMATIZACIONES/` | Zona reservada (vacía de tooling en la base) |
| `04-GENAI/` | Convenciones de IA |

## Decisiones técnicas

**¿Por qué ENTRADA/CEREBRO/RECURSOS y no PARA o LYT "puro"?**

PARA clasifica proyectos/áreas/recursos/archivos; LYT empuja mapas. Aquí la captura (`00`) queda explícita y el "cerebro" agrupa lo que ya tiene significado (mapas, agenda, accionables). Es una mezcla deliberada, no una copia de un framework.

**¿Por qué solo Dataview + Folder Notes?**

Bastan para mapas vivos y notas de carpeta. Más plugins en la base = más fricción al clonar. La pro añade tooling; la base no debería exigir Node.

## Trade-offs y limitaciones

Plantilla **opinada**: si quieres una bóveda mínima de un solo nivel, sobra estructura. Si quieres automatización, esta repo se queda corta a propósito — usa la pro.

## Evidencia de calidad

Checklist de humo (sin Node):

- [ ] Existen las carpetas `00`–`04` e `Inicio.md`
- [ ] Dataview renderiza las queries de Inicio / mapas
- [ ] Folder Notes abre la nota homónima al entrar en una carpeta

## Lecciones aprendidas

Separar base y pro evita que quien solo quiere carpetas arrastre `package.json`. El precio: dos repos que hay que mantener alineados en semántica de carpetas.

## Próximos pasos

1. Enlace explícito y simétrico desde/hacia la plantilla pro.
2. Revisar `03-AUTOMATIZACIONES` en la base (¿README que diga "vacío a propósito"?).
3. Ejemplo mínimo de mapa Dataview comentado para onboarding.
