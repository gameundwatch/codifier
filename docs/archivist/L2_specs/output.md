# output — 出力の要件

## Requirements

<a id="R1"></a>

### R1 出力先を `docs/codifier/` に固定する

- 利用者が変更できない
- 設定項目として露出しない

<a id="R2"></a>

### R2 既にあるドキュメント群を壊さない

- `docs/codifier/` の外へ書き込まない
- 同名のファイルが既にあるときは上書きせず報告する

<a id="R3"></a>

### R3 粒度でディレクトリを分けず一列に置く

- エスカレーションが起きてもファイルは移動しない
- 粒度は記載内容と参照の数から読む

<a id="R4"></a>

### R4 書き込む主体を一つに限る

- 内容を決める側はファイルに触れない
- 出力の規則を守る箇所が一箇所に収まる

## Verify

| No | VERIFY_NAME | REQUIREMENT |
| -- | ----------- | ----------- |
| 1 | [出力先の固定](#V1) | [R1](#R1) |
| 2 | [範囲外への不書き込み](#V2) | [R2](#R2) |
| 3 | [上書きの回避](#V3) | [R2](#R2) |
| 4 | [配置が平坦](#V4) | [R3](#R3) |
| 5 | [昇格で動かない](#V5) | [R3](#R3) |
| 6 | [書き込みの一点](#V6) | [R4](#R4) |

<a id="V1"></a>

### V1 出力先の固定

- Means: checklist
- 出力先を変えようとする指示を与え、受け付けないことを見る

<a id="V2"></a>

### V2 範囲外への不書き込み

- Means: checklist
- 実行前後でリポジトリの差分を取り、`docs/codifier/` の外に変更が無いことを見る

<a id="V3"></a>

### V3 上書きの回避

- Means: checklist
- 同名のファイルを置いた状態で実行し、上書きされず報告が出ることを見る

<a id="V4"></a>

### V4 配置が平坦

- Means: checklist
- 三段すべてを含む出力で、`docs/codifier/` にサブディレクトリが無いことを見る

<a id="V5"></a>

### V5 昇格で動かない

- Means: checklist
- エスカレーションを起こし、対象ファイルのパスが変わらないことを見る

<a id="V6"></a>

### V6 書き込みの一点

- Means: checklist
- 実行中にファイルを書き換える箇所を数え、一つだけであることを見る

## Decisions
- [ファイルへの書き込みは一本に集約する](../L4_decisions/single-writer.md)
- [出力先は固定する](../L4_decisions/output-path-is-fixed.md)
- [出力は一列に並べる](../L4_decisions/flat-output-layout.md)

## References

### Structures

- [output-layout](../L3_structures/output-layout.md)
- [writing-path](../L3_structures/writing-path.md)
- [configurable-surface](../L3_structures/configurable-surface.md)

### Terms

- [granularity](../L3_terms/granularity.md)
- [escalation](../L3_terms/escalation.md)
