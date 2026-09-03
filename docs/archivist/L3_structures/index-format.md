# index-format — 索引の形

## Diagrams

<a id="D1"></a>

### D1 列と出処

```mermaid
flowchart LR
    F["決断ファイル"] --> P[path]
    F --> S[statement]
    F --> G[grounds]
    F --> T[timecode]
    G --> N["granularity<br/>= 他ファイルの grounds を数える"]
    P & S & G & T & N --> C[(索引 CSV)]
```

五列すべてが決断ファイルから導かれる。索引そのものは何も決めない。
granularity だけは一枚では出ず、全ファイルの grounds を数えて決まる。
入次数を列に持たないのは、grounds 列から数えられるため。
列が増減すれば、この図に行が増減する。

<a id="D2"></a>

### D2 索引を読む側

```mermaid
flowchart LR
    C[(索引 CSV)] --> U1[重複の検出]
    C --> U2[粒度の算出]
    C --> U3[循環の検査]
    C --> U4[近傍図の生成]
    C --> U5[先発の判定]
```

全決断を横断する処理は索引だけを読む。決断ファイルを全件開かない。
索引が古いと四つすべてが誤るため、実行のたびに作り直す。

## Decisions
- [索引は CSV で持つ](../L4_decisions/index-is-csv.md)
- [索引は決断発効時の timecode を持つ](../L4_decisions/index-holds-timecode.md)
- [生成された箇所は毎回書き直す](../L4_decisions/generated-parts-are-rewritten.md)
- [粒度は被参照数で決まる](../L4_decisions/granularity-from-reference-count.md)

## References

### Terms

- [index](../L3_terms/index.md)
- [statement](../L3_terms/statement.md)
- [grounds](../L3_terms/grounds.md)
- [granularity](../L3_terms/granularity.md)
