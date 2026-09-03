# index — 索引の要件

## Requirements

<a id="R1"></a>

### R1 索引を CSV 一枚として `docs/codifier/` に置く

- 列は path・statement・granularity・grounds・timecode の五つ
- 入次数を列に持たない
- 値は常に引用符で囲み、内側の引用符は二重にする

<a id="R2"></a>

### R2 全決断が索引に現れる

- 決断ファイルが増減すれば、索引の行も同じだけ増減する
- 索引にあって実体の無い行、実体があって索引に無い決断のどちらも残さない

<a id="R3"></a>

### R3 全決断を横断する処理は索引だけを読む

- 重複の検出、粒度の算出、循環の検査、近傍図の生成の四つが対象
- 決断ファイルを全件開かない

<a id="R4"></a>

### R4 索引は実行のたびに作り直す

- 手で編集された内容は次の実行で消える
- 作り直しは書き込みを担う一点が行う

## Verify

| No | VERIFY_NAME | REQUIREMENT |
| -- | ----------- | ----------- |
| 1 | [列と引用](#V1) | [R1](#R1) |
| 2 | [行と実体の一致](#V2) | [R2](#R2) |
| 3 | [読む範囲](#V3) | [R3](#R3) |
| 4 | [作り直し](#V4) | [R4](#R4) |

<a id="V1"></a>

### V1 列と引用

- Means: checklist
- 引用符とカンマを含む statement を持つ決断を与え、CSV が壊れずに読み戻せることを見る

<a id="V2"></a>

### V2 行と実体の一致

- Means: checklist
- 決断を一件足し一件消した後、索引の行数と `docs/codifier/` の決断ファイル数が一致することを見る

<a id="V3"></a>

### V3 読む範囲

- Means: checklist
- 決断が多数ある状態で重複検出を走らせ、開かれたファイルが索引だけであることを見る

<a id="V4"></a>

### V4 作り直し

- Means: checklist
- 索引を手で書き換えてから実行し、書き換えが残らないことを見る

## Decisions
- [索引は CSV で持つ](../L4_decisions/index-is-csv.md)
- [索引は決断発効時の timecode を持つ](../L4_decisions/index-holds-timecode.md)
- [生成された箇所は毎回書き直す](../L4_decisions/generated-parts-are-rewritten.md)
- [ファイルへの書き込みは一本に集約する](../L4_decisions/single-writer.md)

## References

### Structures

- [index-format](../L3_structures/index-format.md)

### Terms

- [index](../L3_terms/index.md)
- [statement](../L3_terms/statement.md)
- [grounds](../L3_terms/grounds.md)
- [granularity](../L3_terms/granularity.md)
