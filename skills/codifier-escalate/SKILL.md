---
name: codifier-escalate
description: Count in-degree from the index and settle each article's granularity, adding the rationale a raised step requires. Use after articles are added, merged, or removed.
---

# codifier-escalate

Granularity is counted, not declared. **Return instructions; never write.**

## What to read

`docs/codifier/index.csv`, and `docs/codifier/config.json` when it exists.
Count the `grounds` column: a article's in-degree is how many rows name it.

## The three steps

| Granularity | Held when | Carries |
| --- | --- | --- |
| choice | below the first threshold | statement, timecode, grounds |
| convention | at or above the first | and a rationale of one line |
| principle | at or above the second | and a rationale of several lines |

Nobody names the step. It follows from the count, and the same graph gives the same
answer to whoever counts it.

## Thresholds

From `config.json`. When the file is absent, use the defaults - and treat a default
as a starting point, not a rule. How many times a thing must be followed before it
is a convention depends on how long the project has been running.

## It only goes up

Compare the counted step against the one the file already holds and take the larger.
**Never emit an instruction that lowers a step.** References disappear - articles
are overturned, duplicates are merged away - and the count falls with them. The
rationale already written stays written.

## What a raised step changes

Add the rationale section, nothing else. Statement, timecode and grounds are
untouched, and **the file does not move.** A path that changed with granularity
would break every reference to it from outside.

## What comes back

- the articles whose step rose, from what to what
- for each, the section to add

## Language

Write the report in the language the project's existing documents use.
