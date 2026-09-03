# granularity-ladder — 粒度の段とエスカレーション

## Diagrams

<a id="D1"></a>

### D1 粒度の遷移

```mermaid
stateDiagram-v2
    [*] --> choice
    choice --> convention: 被参照数 >= N
    convention --> principle: 被参照数 >= M
```

三段しかなく、遷移は下から上への二本だけ。
戻る矢印が無いことがエスカレーションの不可逆を表す。
N と M は利用者が決める閾値で、既定値を持つが規則ではない。
段が増減すれば状態が増減し、降格を認めれば逆向きの矢印が現れる。

<a id="D2"></a>

### D2 粒度ごとの記載内容

```mermaid
flowchart TD
    subgraph P[principle]
        pa[statement]
        pt[timecode]
        pb[rationale 複数行]
        pz[grounds]
    end
    subgraph C[convention]
        ca[statement]
        ct[timecode]
        cb[rationale 単一行]
        cz[grounds]
    end
    subgraph H[choice]
        ha[statement]
        ht[timecode]
        hz[grounds]
    end
```

粒度が上がるほど欄が増える。増えるのは rationale だけで、statement・timecode・grounds は
三段に共通する。
choice に rationale が無いのは、誰も拠って立っていない決断に説明責任が生じないため。
不可逆であることと合わせると、欄は増える方向にしか変わらない。

## Decisions
- [粒度は choice / convention / principle の三段とする](../L4_decisions/three-granularities.md)
- [粒度が上がるほど記載内容が増える](../L4_decisions/content-grows-with-granularity.md)
- [エスカレーションは不可逆とする](../L4_decisions/escalation-is-irreversible.md)
- [エスカレーションの閾値は利用者が決める](../L4_decisions/thresholds-are-configurable.md)
- [粒度は被参照数で決まる](../L4_decisions/granularity-from-reference-count.md)
- [決断は発効時刻を欄として持つ](../L4_decisions/decision-holds-timecode.md)

## References

### Terms

- [granularity](../L3_terms/granularity.md)
- [choice](../L3_terms/choice.md)
- [convention](../L3_terms/convention.md)
- [principle](../L3_terms/principle.md)
- [escalation](../L3_terms/escalation.md)
- [statement](../L3_terms/statement.md)
- [rationale](../L3_terms/rationale.md)
- [grounds](../L3_terms/grounds.md)
- [timecode](../L3_terms/timecode.md)
