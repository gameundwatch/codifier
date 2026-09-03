# writing-path — 書き込みの経路

## Diagrams

<a id="D1"></a>

### D1 書き込みは一点を通る

```mermaid
flowchart LR
    A[書く内容を決める側] --> W[書き込み]
    B[書く内容を決める側] --> W
    C[書く内容を決める側] --> W
    W --> O["決断ファイル"]
    W --> X[(索引 CSV)]
    W --> Y[各決断の近傍図]
    A -.->|不可| O
    B -.->|不可| O
    C -.->|不可| O
```

内容を決める側はいくつあってもよいが、ファイルに触れるのは一点だけ。
索引と近傍図も同じ一点が作り直す。
出力先の固定と一列配置は、この一点だけが守る。
破線が引けてしまう状態は、規則の写しがそこに生まれていることを意味する。

## Decisions
- [ファイルへの書き込みは一本に集約する](../L4_decisions/single-writer.md)
- [書き込みはオーケストレーターが持つ](../L4_decisions/orchestrator-writes.md)
- [出力先は固定する](../L4_decisions/output-path-is-fixed.md)
- [出力は一列に並べる](../L4_decisions/flat-output-layout.md)
- [生成された箇所は毎回書き直す](../L4_decisions/generated-parts-are-rewritten.md)

## References

### Structures

- [output-layout](../L3_structures/output-layout.md)

### Terms

- [decision](../L3_terms/decision.md)
- [index](../L3_terms/index.md)
- [neighborhood](../L3_terms/neighborhood.md)
