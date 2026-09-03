---
name: codifier-collect
description: Read a codebase and its history and raise the decisions already settled there, judged by sign alone. Use when decisions have to be recovered from what a project has already done.
---

# codifier-collect

Raise what is already settled. **Return it; never write it.**

## What to read

Code and history, both. Code holds only the option that was taken - what was
discarded lives in the commits. Reading code alone recovers the chosen option and
calls it a decision, which it is not.

## Scope first

Ask what to work on, or use what the user named: a directory, a file, a range of
commits. **Never take the whole repository on your own initiative.**

Say how many files and how many commits are in scope before starting. If that
number is large, propose a smaller first pass.

## The four signs

Raise a candidate when the range shows one of these. One is enough.

| Sign | What it looks like |
| --- | --- |
| repetition | the same shape in N places, with no trace of an alternative |
| convergence | changed A to B to C, then stopped |
| reversion | B was introduced and then reverted to A |
| stillness | the surroundings changed repeatedly and this did not |

Anything carrying none of the four is not settled. Do not raise it.

## Do not ask

The whole point is that the evidence is already in the history. Once the scope is
fixed, run to the end without putting a question to anyone. Judgement is the
presence of a sign, nothing else.

## Timecode

Every candidate carries the time of the commit where its sign settled - the last
commit that completed the pattern. **Not the time of this run.** Collecting the
same range on a different day must produce the same value.

## What comes back

- the candidates, each with a statement, a timecode, and the commits it was read from
- what was passed over, each with which sign it lacked

The second list is not optional. A silent omission cannot be argued with.

## Language

Write statements in the language the project's existing documents use.
