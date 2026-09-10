---
name: codifier
description: Collect the articles already settled in a codebase and write them to docs/codifier/. Calls the four workers, then writes. Use when a project has articles buried in its code and history that were never recorded.
---

# codifier

Call the four, then write. **The four never touch a file. This one does.**

Read `TEMPLATE.md` in this directory for the form an article takes.

## Input

A scan range the user names: a directory, a file, a range of commits. Ask for it
before starting. **Never take the whole repository on your own initiative.**

## Order

```
1. codifier-collect   range              -> candidates, each carrying a timecode
2. codifier-disjoint  candidates, index  -> duplicates, merge instructions
3. codifier-escalate  settled set, index -> granularity per article
4. codifier-graph     settled set, index -> cycle report, neighbourhood diagrams
5. write
```

Nothing reaches disk before step 5. A cycle reported in step 4 stops the run:
report it and write nothing.

## Writing

Everything goes under `docs/codifier/`, and nothing goes anywhere else. The path is
fixed; do not accept a replacement for it.

- One article per file, all in one flat directory. No subdirectory per granularity
- A file name never carries the granularity - escalation must not move a file
- An article file a person wrote is never overwritten. On a name collision, report
  and stop
- `index.csv` and the neighbourhood diagrams are generated. Rewrite them whole on
  every run

## The index

`docs/codifier/index.csv`, five columns, no header:

```
path,statement,granularity,grounds,timecode
```

Every value is quoted, and a `"` inside one is doubled to `""`. `grounds` holds the
paths this article rests on, separated by `;`. In-degree is not a column - count
the `grounds` column instead.

Rebuild it from the article files alone. Deleting it must lose nothing.

## Timecode

Take what `codifier-collect` returns and write it into the article file. **Never
stamp the time of writing.** The value is the time the article settled, and running
the same range twice must produce the same value.

## Configuration

`docs/codifier/config.json`, read only. It carries the escalation thresholds.
When it is absent, use the defaults - a default is a starting point, not a rule.

## Stopping

On reaching something the articles do not settle, stop without writing it and say
what is missing. Filling that gap is an article, and articles are not made here.

## Language

Write articles in the language the project's existing documents use. Where none
exist, follow the language of the code comments and commit messages. Field names
stay in English - they are form, not prose.
