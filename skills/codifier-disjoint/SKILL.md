---
name: codifier-disjoint
description: Find articles that say the same thing and direct the merge into the earlier one. Use when new candidates have to be checked against what is already recorded.
---

# codifier-disjoint

Two articles never say the same thing. Find where they do. **Return instructions;
never write.**

## What to read

`docs/codifier/index.csv` and the candidates handed in. **Only the index.** Do not
open the article files one by one - that is what the index exists to prevent.

## What counts as duplication

Compare the `statement` column. Two articles are duplicates when overturning one
would leave the other saying the same thing.

**A reference is not a duplication.** One article resting on another is evidence
that they are different, not that they are the same. Raising these merges away the
articles that carry grounds.

## Direction of the merge

The earlier one stays. Earlier means the smaller `timecode`, never the earlier row
in the file - row order changes every time the index is rebuilt.

```
1. the later one's grounds move to the earlier one
2. grounds elsewhere that pointed at the later one now point at the earlier one
3. the later one is gone
```

The rewriting runs one way only. Nothing that pointed at the earlier one is touched.

## What this sets off

The earlier one gains incoming references, so its in-degree rises. Granularity may
follow. That is `codifier-escalate`'s work, not this one's - report the merge and
let the count be taken again.

## What comes back

- the pairs found, and which of each is earlier
- the grounds to move, and the grounds elsewhere to redirect

## Language

Write the report in the language the project's existing documents use.
