---
aliases: []
created: 2026-06-17
draft: false
in:
  - "[[MAPAS]]"
tags:
  - conocimientos
  - map
  - personas
title: Personas
type: Map
updated: 2026-06-18
status: done
---

# Personas

## Sin ficha

Personas referenciadas, al menos `5` veces, en `people` (AGENDA / REGISTRO) sin ficha `type: People` en esta carpeta.

```dataviewjs
const PERSONAS_PREFIX = "01-CEREBRO/CONOCIMIENTOS/PERSONAS/";

function flatPeople(page) {
  if (!page.people) return [];
  return Array.isArray(page.people) ? page.people.flat() : [page.people];
}

function normalizeLink(item) {
  if (!item) return null;
  if (typeof item === "object" && (item.path != null || item.display != null)) return item;
  const text = String(item).trim();
  const match = text.match(/\[\[([^|\]]+)(?:\|([^\]]+))?\]\]/);
  if (!match) return null;
  const target = match[1].trim();
  const display = match[2]?.trim();
  return display ? dv.fileLink(target, display) : dv.fileLink(target);
}

function hasFicha(link) {
  const page = dv.page(link);
  return page?.type === "People" && page.file.path.startsWith(PERSONAS_PREFIX);
}

function orphanKey(link) {
  const page = dv.page(link);
  if (page?.type === "People") return page.file.path;
  if (link.path) return link.path;
  return `unresolved:${link.display ?? String(link)}`;
}

const sources = dv.pages('"01-CEREBRO/AGENDA" OR "01-CEREBRO/PASADO/REGISTRO"')
  .where(p => p.people);

const orphanCounts = new Map();

for (const page of sources) {
  for (const raw of flatPeople(page)) {
    const link = normalizeLink(raw);
    if (!link || hasFicha(link)) continue;
    const key = orphanKey(link);
    const prev = orphanCounts.get(key);
    orphanCounts.set(key, {
      count: (prev?.count ?? 0) + 1,
      link: prev?.link ?? link,
      name: link.display ?? key.split("/").pop()?.replace(/\.md$/, "") ?? key,
    });
  }
}

const rows = [...orphanCounts.values()]
  .filter(p => p.count >= 5)
  .sort((a, b) => b.count - a.count || a.name.localeCompare(b.name, "es"));

if (!rows.length) {
  dv.paragraph("Ninguna.");
} else {
  dv.table(
    ["Persona", "Referencias"],
    rows.map(({ link, count }) => [link, count])
  );
}
```

## Top 10 por contactar

```dataviewjs
const people = dv.pages('"01-CEREBRO/CONOCIMIENTOS/PERSONAS"')
  .where(p => p.type === "People" && !p.file.tags.includes("meta") && p.file.name !== "yo");

const journals = dv.pages('"01-CEREBRO/PASADO/REGISTRO"');

function flatPeople(page) {
  if (!page.people) return [];
  return Array.isArray(page.people) ? page.people.flat() : [page.people];
}

function lastContact(person) {
  const dates = journals
    .where(j => flatPeople(j).some(link => link?.path === person.file.path))
    .map(j => j["journal-date"])
    .filter(Boolean);

  if (!dates.length) return null;
  return dates.sort((a, b) => b.ts - a.ts)[0];
}

const rows = [...people]
  .map(p => ({ person: p, last: lastContact(p) }));

rows.sort((a, b) => {
  const pa = a.person?.["contact-priority"] ?? 999;
  const pb = b.person?.["contact-priority"] ?? 999;
  if (pa !== pb) return pa - pb;

  const da = a.last?.ts ?? 0;
  const db = b.last?.ts ?? 0;
  if (da !== db) return da - db;

  return a.person.file.name.localeCompare(b.person.file.name, "es");
});

const top10 = rows.slice(0, 10);

dv.table(
  ["Persona", "Último contacto", "Grupos"],
  top10.map(({ person, last }) => [
    person.file.link,
    last ? last.toFormat("dd/MM/yyyy") : "—",
    person.in?.join(" · ") ?? "—",
  ])
);
```

## Cumpleaños (en los próximos 30 días)

```dataview
TABLE WITHOUT ID
  file.link AS "Persona",
  dateformat(birthdate, "dd/MM") AS "Cumpleaños",
  join(in) AS "Grupos"
FROM "01-CEREBRO/CONOCIMIENTOS/PERSONAS" AND -#meta
WHERE birthdate
  AND birthdate >= date(today)
  AND birthdate <= date(today) + dur(30 days)
  AND !contains(file.name, "yo")
SORT birthdate ASC
```

## Grupos

## Amistades

```dataview
TABLE WITHOUT ID
  file.link AS "Persona",
  join(in) AS "Grupos"
FROM "01-CEREBRO/CONOCIMIENTOS/PERSONAS" AND -#meta
WHERE contains(in, link("Amistades"))
SORT name ASC, surname ASC
```

## Emprender

```dataview
TABLE WITHOUT ID
  file.link AS "Persona",
  join(in) AS "Grupos"
FROM "01-CEREBRO/CONOCIMIENTOS/PERSONAS" AND -#meta
WHERE contains(in, link("Emprender"))
SORT name ASC, surname ASC
```

## Abi Global Health

```dataview
TABLE WITHOUT ID
  file.link AS "Persona",
  join(in) AS "Grupos"
FROM "01-CEREBRO/CONOCIMIENTOS/PERSONAS" AND -#meta
WHERE contains(in, link("Abi Global Health"))
SORT name ASC, surname ASC
```

## Be Disruptive

```dataview
TABLE WITHOUT ID
  file.link AS "Persona",
  join(in) AS "Grupos"
FROM "01-CEREBRO/CONOCIMIENTOS/PERSONAS" AND -#meta
WHERE contains(in, link("Be Disruptive"))
SORT name ASC, surname ASC
```

## BTC Tech Management & Leadership

```dataview
TABLE WITHOUT ID
  file.link AS "Persona",
  join(in) AS "Grupos"
FROM "01-CEREBRO/CONOCIMIENTOS/PERSONAS" AND -#meta
WHERE contains(in, link("BTC Tech Management & Leadership"))
SORT name ASC, surname ASC
```

## HuMaIND x Labs

```dataview
TABLE WITHOUT ID
  file.link AS "Persona",
  join(in) AS "Grupos"
FROM "01-CEREBRO/CONOCIMIENTOS/PERSONAS" AND -#meta
WHERE contains(in, link("HuMaIND x Labs"))
SORT name ASC, surname ASC
```

## Linux Center

```dataview
TABLE WITHOUT ID
  file.link AS "Persona",
  join(in) AS "Grupos"
FROM "01-CEREBRO/CONOCIMIENTOS/PERSONAS" AND -#meta
WHERE contains(in, link("Linux Center"))
SORT name ASC, surname ASC
```

## Rankia

```dataview
TABLE WITHOUT ID
  file.link AS "Persona",
  join(in) AS "Grupos"
FROM "01-CEREBRO/CONOCIMIENTOS/PERSONAS" AND -#meta
WHERE contains(in, link("Rankia"))
SORT name ASC, surname ASC
```

## Slimbook

```dataview
TABLE WITHOUT ID
  file.link AS "Persona",
  join(in) AS "Grupos"
FROM "01-CEREBRO/CONOCIMIENTOS/PERSONAS" AND -#meta
WHERE contains(in, link("Slimbook"))
SORT name ASC, surname ASC
```

## Stack&Flow

```dataview
TABLE WITHOUT ID
  file.link AS "Persona",
  join(in) AS "Grupos"
FROM "01-CEREBRO/CONOCIMIENTOS/PERSONAS" AND -#meta
WHERE contains(in, link("Stack&Flow"))
SORT name ASC, surname ASC
```

## Valencia Toastmasters

```dataview
TABLE WITHOUT ID
  file.link AS "Persona",
  join(in) AS "Grupos"
FROM "01-CEREBRO/CONOCIMIENTOS/PERSONAS" AND -#meta
WHERE contains(in, link("Valencia Toastmasters"))
SORT name ASC, surname ASC
```

## ValenciaJS

```dataview
TABLE WITHOUT ID
  file.link AS "Persona",
  join(in) AS "Grupos"
FROM "01-CEREBRO/CONOCIMIENTOS/PERSONAS" AND -#meta
WHERE contains(in, link("ValenciaJS"))
SORT name ASC, surname ASC
```

## WordPress Valencia

```dataview
TABLE WITHOUT ID
  file.link AS "Persona",
  join(in) AS "Grupos"
FROM "01-CEREBRO/CONOCIMIENTOS/PERSONAS" AND -#meta
WHERE contains(in, link("WordPress Valencia"))
SORT name ASC, surname ASC
```

## Xinxeta Multimedia Studio

```dataview
TABLE WITHOUT ID
  file.link AS "Persona",
  join(in) AS "Grupos"
FROM "01-CEREBRO/CONOCIMIENTOS/PERSONAS" AND -#meta
WHERE contains(in, link("Xinxeta Multimedia Studio"))
SORT name ASC, surname ASC
```

## Todas las fichas

```dataviewjs
const people = dv.pages('"01-CEREBRO/CONOCIMIENTOS/PERSONAS"')
  .where(p => p.type === "People" && !p.file.tags.includes("meta") && p.file.name !== "yo");

const journals = dv.pages('"01-CEREBRO/PASADO/REGISTRO"');

function flatPeople(page) {
  if (!page.people) return [];
  return Array.isArray(page.people) ? page.people.flat() : [page.people];
}

function lastContact(person) {
  const dates = journals
    .where(j => flatPeople(j).some(link => link?.path === person.file.path))
    .map(j => j["journal-date"])
    .filter(Boolean);

  if (!dates.length) return null;
  return dates.sort((a, b) => b.ts - a.ts)[0];
}

const rows = [...people]
  .map(p => ({ person: p, last: lastContact(p) }));

rows.sort((a, b) => {
  const pa = a.person?.["contact-priority"] ?? 999;
  const pb = b.person?.["contact-priority"] ?? 999;
  if (pa !== pb) return pa - pb;

  const da = a.last?.ts ?? 0;
  const db = b.last?.ts ?? 0;
  if (da !== db) return da - db;

  return a.person.file.name.localeCompare(b.person.file.name, "es");
});

dv.table(
  ["Persona", "Último contacto", "Grupos"],
  rows.map(({ person, last }) => [
    person.file.link,
    last ? last.toFormat("dd/MM/yyyy") : "—",
    person.in?.join(" · ") ?? "—",
  ])
);
```
