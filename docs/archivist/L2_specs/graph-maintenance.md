# graph-maintenance — 参照グラフを保つ要件

## Requirements

<a id="R1"></a>

### R1 参照は循環しない

- 循環を検出したときは報告し、書き込まない
- 検査は決断を追加または削除するたびに行う

<a id="R2"></a>

### R2 層構造を強制しない

- choice が convention を経ずに principle を参照してよい
- 粒度の順序で参照の可否を判定しない

<a id="R3"></a>

### R3 覆った箇所は打ち消し線で消す

- 行は残す
- ファイルの内容が全て覆ったときはファイルごと削除する

<a id="R4"></a>

### R4 削除された決断への参照を根拠欄から消す

- 消えるのは grounds の一行のみ
- 参照していた決断そのものは覆らず、連鎖して削除されない

## Verify

| No | VERIFY_NAME | REQUIREMENT |
| -- | ----------- | ----------- |
| 1 | [循環の検出](#V1) | [R1](#R1) |
| 2 | [層を跨ぐ参照](#V2) | [R2](#R2) |
| 3 | [打ち消しと削除](#V3) | [R3](#R3) |
| 4 | [波及がそこで止まる](#V4) | [R4](#R4) |

<a id="V1"></a>

### V1 循環の検出

- Means: checklist
- 循環する参照を含む決断群を与え、報告が出て書き込みが行われないことを見る

<a id="V2"></a>

### V2 層を跨ぐ参照

- Means: checklist
- choice が principle を直接参照する入力を与え、拒否されないことを見る

<a id="V3"></a>

### V3 打ち消しと削除

- Means: checklist
- 一部だけ覆した決断で行が残り、全て覆した決断でファイルが消えることを見る

<a id="V4"></a>

### V4 波及がそこで止まる

- Means: checklist
- 削除された決断を参照していた決断が残り、grounds から一行だけ消えていることを見る

## Decisions
- [参照はグラフであり、循環しない](../L4_decisions/references-form-a-dag.md)
- [覆った内容は打ち消し線で消す](../L4_decisions/overturned-is-struck-through.md)
- [削除された決断への参照は連携して消す](../L4_decisions/cascade-delete-references.md)

## References

### Structures

- [reference-graph](../L3_structures/reference-graph.md)
- [decision-removal](../L3_structures/decision-removal.md)

### Terms

- [reference](../L3_terms/reference.md)
- [overturn](../L3_terms/overturn.md)
- [grounds](../L3_terms/grounds.md)
