# granularity — 粒度の要件

## Requirements

<a id="R1"></a>

### R1 粒度は被参照数から決まる

- 書き手が粒度を指定できない
- 同じグラフからは誰が数えても同じ粒度が出る

<a id="R2"></a>

### R2 粒度は choice / convention / principle の三段とする

- 四段目を設けない
- principle が ADR に相当する

<a id="R3"></a>

### R3 粒度ごとに記載する欄が変わる

- 三段すべてが statement・timecode・grounds を持つ
- choice は rationale を持たない
- convention は rationale を単一行で持つ
- principle は rationale を複数行で持つ

<a id="R4"></a>

### R4 エスカレーションは不可逆とする

- 被参照数が閾値を割っても粒度は下がらない
- 一度書いた rationale を機械的に消さない

<a id="R5"></a>

### R5 閾値は利用者が決める

- choice から convention、convention から principle の二つを設定できる
- 設定は `docs/codifier/config.json` に置く
- 設定が無いときは既定値で動く

## Verify

| No | VERIFY_NAME | REQUIREMENT |
| -- | ----------- | ----------- |
| 1 | [粒度の再現性](#V1) | [R1](#R1) |
| 2 | [段の数](#V2) | [R2](#R2) |
| 3 | [欄の増減](#V3) | [R3](#R3) |
| 4 | [降格しない](#V4) | [R4](#R4) |
| 5 | [閾値の設定](#V5) | [R5](#R5) |

<a id="V1"></a>

### V1 粒度の再現性

- Means: checklist
- 同じ条項群を二度処理し、各ファイルの粒度が一致することを見る

<a id="V2"></a>

### V2 段の数

- Means: checklist
- 出力された条項の粒度が三種のいずれかに収まることを見る

<a id="V3"></a>

### V3 欄の増減

- Means: checklist
- 三段それぞれの条項を出力させ、statement・timecode・grounds が三段すべてに在り、
  choice に rationale が無く、convention が単一行、principle が複数行であることを見る

<a id="V4"></a>

### V4 降格しない

- Means: checklist
- principle を参照していた条項を削除し、被参照数が閾値を割った後も
  粒度と rationale が残ることを見る

<a id="V5"></a>

### V5 閾値の設定

- Means: checklist
- 閾値を変えて同じ入力を処理し、粒度の分布が変わることを見る

## Decisions
- [粒度は被参照数で決まる](../L4_decisions/granularity-from-reference-count.md)
- [条項は発効時刻を欄として持つ](../L4_decisions/article-holds-timecode.md)
- [粒度は choice / convention / principle の三段とする](../L4_decisions/three-granularities.md)
- [粒度が上がるほど記載内容が増える](../L4_decisions/content-grows-with-granularity.md)
- [エスカレーションは不可逆とする](../L4_decisions/escalation-is-irreversible.md)
- [エスカレーションの閾値は利用者が決める](../L4_decisions/thresholds-are-configurable.md)
- [設定は `docs/codifier/config.json` に置く](../L4_decisions/config-in-output-dir.md)

## References

### Structures

- [granularity-ladder](../L3_structures/granularity-ladder.md)

### Terms

- [granularity](../L3_terms/granularity.md)
- [escalation](../L3_terms/escalation.md)
- [statement](../L3_terms/statement.md)
- [rationale](../L3_terms/rationale.md)
- [grounds](../L3_terms/grounds.md)
- [timecode](../L3_terms/timecode.md)
