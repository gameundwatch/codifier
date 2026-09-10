# skill-composition — スキルの構成

## Diagrams

<a id="D1"></a>

### D1 構成と書き込みの向き

```mermaid
flowchart LR
    O["/codifier"]
    O --> C["/codifier-collect"]
    O --> D["/codifier-disjoint"]
    O --> G["/codifier-graph"]
    O --> E["/codifier-escalate"]
    C -.内容を返す.-> O
    D -.内容を返す.-> O
    G -.内容を返す.-> O
    E -.内容を返す.-> O
    O ==> W["docs/codifier/"]
```

四本は内容を返すだけで、ファイルに触れない。実線が呼び出し、破線が戻り、
二重線が書き込みで、二重線は一本しか無い。
四本のいずれかから `docs/codifier/` へ線が引ける状態は、規則の写しが生まれている。

<a id="D2"></a>

### D2 コマンドと要件の対応

```mermaid
flowchart LR
    S1["/codifier-collect"] ---|1対1| R1[collection]
    S2["/codifier-disjoint"] ---|1対1| R2[disjointness]
    S3["/codifier-graph"] ---|1対1| R3[graph-maintenance]
    S4["/codifier-escalate"] ---|1対1| R4[granularity]
    S0["/codifier"] ---|1対2| R5[output]
    S0 ---|1対2| R6[index]
```

四本は要件一枚と一対一に対応する。オーケストレーターだけが二枚を負う。
output と index はどの仕事にも属さず、書き込みに従う制約であるため。
片方だけが増えた状態は、起動できるのに要件が無いか、要件だけあって起動できないかを
意味する。

## Decisions
- [スキルは仕事ごとに四つに割る](../L4_decisions/skill-per-job.md)
- [書き込みはオーケストレーターが持つ](../L4_decisions/orchestrator-writes.md)
- [ファイルへの書き込みは一本に集約する](../L4_decisions/single-writer.md)

## References

### Structures

- [writing-path](../L3_structures/writing-path.md)

### Terms

- [article](../L3_terms/article.md)
- [index](../L3_terms/index.md)
