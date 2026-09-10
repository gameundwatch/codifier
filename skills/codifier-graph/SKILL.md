---
name: codifier-graph
description: Check the reference graph for cycles, work out what an overturned article takes with it, and build each article's neighbourhood diagram. Use before writing, and after anything is removed.
---

# codifier-graph

Keep the graph readable and acyclic. **Return findings and diagrams; never write.**

## What to read

`docs/codifier/index.csv`, and the settled set handed in. Build the edges from the
`grounds` column: an edge runs from the citing article to the one it rests on.

## Cycles

A cycle leaves no way to say which article is the original. Report it and let the
run stop. Nothing is written while one stands.

## Layers are not enforced

A `choice` may rest on a `principle` directly, with no `convention` between them.
Granularity orders nothing. **Never refuse a reference for crossing steps** - the
graph is a graph, not a ladder.

## Overturning

- part of a file overturned: strike the line through. The line stays, so what
  changed can still be read
- every line overturned: the file goes. A file of nothing but struck-through lines
  sits among the live ones and reads as one of them

When a file goes, find the `grounds` entries that name it and drop those lines.
**One line each, and it ends there.** The articles that cited it are not overturned
and are not deleted - a deletion that cascaded would take the whole graph with it.

## Neighbourhood

One diagram per article, held in that article's own file. There is no diagram of
the whole graph anywhere.

```
outgoing  three hops
incoming  one hop
```

The asymmetry is the point. In-degree is granularity, so following incoming edges
deep makes a principle's diagram grow until it is the whole graph again. Outgoing
edges do not grow with granularity. **The same limits apply at all three steps** -
do not vary the depth by granularity.

## What comes back

- cycles, if any
- the lines to strike, the files to delete, the grounds entries to drop
- a neighbourhood diagram per article

## Language

Write the report in the language the project's existing documents use.
