<!--
    LARGE_SNAKE_CASE is a placeholder. Replace every one with content.
    Everything else is written as it stands, field names included.
    A line holding only `...` means repeat as needed; delete the line.
-->

# STATEMENT

<!--
    The title is the statement: one line, what was decided.
    No two articles say the same thing here. This line is what duplicate
    detection compares.
-->

- Timecode: ISO_8601
- Granularity: choice | convention | principle

<!--
    Timecode is when the article settled - the commit's time, not the time this
    file was written. Granularity is derived from how many other articles cite
    this one; it is never chosen by hand, and it never goes down.
-->

## Rationale

<!--
    Omit this section entirely for `choice`.
    One line for `convention`. Several lines for `principle`.
    What is carried here grows with granularity, and is never removed once written.
-->

RATIONALE

## Grounds

### References

<!-- Articles this one rests on. These are the outgoing edges. -->

- [STATEMENT_1](./DECISION_FILE_1.md)
- [STATEMENT_2](./DECISION_FILE_2.md)
...

### Implementation

<!-- The commits and files the article was read from -->

- COMMIT_SHA — WHAT_IT_SHOWS
- FILE_PATH
...

## Neighborhood

<!--
    Generated. Do not edit by hand - it is rebuilt on every run.
    Outgoing edges three hops, incoming edges one hop.
-->

```mermaid
graph TD
```

<!--
    A struck-through line is one that has been overturned. Keep the line.
    When every line in the file is struck through, the file is deleted instead,
    and the reference to it is dropped from the Grounds of whatever cited it.
-->
