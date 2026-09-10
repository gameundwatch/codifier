---
name: codifier-collect
description: Read a codebase and its history and raise the articles already settled there, through two entries - signs in the history and definitions in the code. Use when articles have to be recovered from what a project has already done.
---

# codifier-collect

Raise what is already settled. **Return it; never write it.**

## Two entries

There are two, and they are not merged.

| Entry | Read from | Sieve | Discarded option |
| --- | --- | --- | --- |
| sign | history | one of the four signs | held |
| definition | code | named from outside the defining scope | none |

A article needing a discarded option cannot be recovered from code alone - code
keeps only the option that was taken. But a definition is the act of binding a
name to a thing, and that act is itself the article. It needs no reason, so it
needs no evidence, and it does not stand as a fifth sign.

## Scope first

Ask what to work on, or use what the user named: a directory, a file, a range of
commits. **Never take the whole repository on your own initiative.**

Say how many files and how many commits are in scope before starting. If that
number is large, propose a smaller first pass.

## The four signs

The history entry. Raise a candidate when the range shows one of these. One is
enough.

| Sign | What it looks like |
| --- | --- |
| repetition | the same shape in N places, with no trace of an alternative |
| convergence | changed A to B to C, then stopped |
| reversion | B was introduced and then reverted to A |
| stillness | the surroundings changed repeatedly and this did not |

Anything carrying none of the four is not settled. Do not raise it. **Four is the
count; do not add a fifth.**

## The sieve on definitions

The code entry. A definition on its own sieves nothing - a binding inside a
function is a definition too. What sieves is being named from outside the scope
it was defined in.

- Count namings in the body and in the tests, both
- Do not count a mention in documentation. Documentation breaks unnoticed, so it
  is no evidence that a name cannot be changed
- Do not judge by visibility. `export`, `pub`, access modifiers differ per
  language, and the spec would never close
- A public identifier nobody names has broken nothing yet. Do not raise it

## What a naming candidate holds

One candidate per name. **Never fold namings into a rule** - if the same shape
repeats, escalation raises it to `convention` on in-degree alone.

- the name
- what it names
- where it can be named from
- whether a second spelling for the same concept coexists, if one does. Record
  the coexistence; leave resolving it to the user

Do not carry depth of exposure as an attribute. A deep identifier simply draws
more references, and granularity already holds that.

## Renaming

A public identifier renamed after its naming article was raised is an overturn.
Return it as one. **Never quietly rewrite the statement of an existing naming
article** - rewriting loses the discarded option, and with it the fact that a
rename happened at all. Past rename commits belong in the `Implementation` list
under `Grounds`, and never raise granularity to earn a rationale field.

## Do not ask

The whole point is that the evidence is already in the history. Once the scope is
fixed, run to the end without putting a question to anyone. Judgement is the
presence of a sign or of a naming from outside, nothing else.

## Timecode

Every candidate carries a commit's time, **never the time of this run**.
Collecting the same range on a different day must produce the same value.

- sign entry: the last commit that completed the pattern
- definition entry: the commit where it was first named from outside

## What comes back

- the candidates, each with a statement, a timecode, and the commits it was read
  from
- the counts, **split by entry** - how many from history, how many from
  definitions. Never a single combined number
- what was passed over, each with which sign it lacked, or that nothing named it

The last list is not optional. A silent omission cannot be argued with.

## Language

Write statements in the language the project's existing documents use.
