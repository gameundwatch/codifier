# disjointness — 互いに素を保つ要件

## Requirements

<a id="R1"></a>

### R1 二枚の決断が同じことを言わない

- 判定は statement の内容で行う
- 参照関係を持つことは重複と見なさない

<a id="R2"></a>

### R2 重複を検出したら先発へ統合する

- 先に置かれた側を残し、後発を消す
- 後発だけが持っていた grounds は先発へ移す

<a id="R3"></a>

### R3 統合後は参照先を先発へ繋ぎ直す

- 後発を参照していた決断の grounds を書き換える
- 繋ぎ直しの結果、先発の粒度が上がることがある

## Verify

| No | VERIFY_NAME | REQUIREMENT |
| -- | ----------- | ----------- |
| 1 | [重複の検出](#V1) | [R1](#R1) |
| 2 | [先発が残る](#V2) | [R2](#R2) |
| 3 | [参照の繋ぎ直し](#V3) | [R3](#R3) |

<a id="V1"></a>

### V1 重複の検出

- Means: checklist
- 同じことを言う二枚を含む入力を与え、重複として報告されることを見る

<a id="V2"></a>

### V2 先発が残る

- Means: checklist
- 統合後、先に置かれた側のファイルが残り、後発が消えていることを見る

<a id="V3"></a>

### V3 参照の繋ぎ直し

- Means: checklist
- 後発を参照していた決断の grounds が先発を指すよう書き換わっていることを見る

## Decisions
- [決断は互いに素である](../L4_decisions/decisions-are-disjoint.md)
- [重複は先発に統合する](../L4_decisions/merge-into-the-earlier.md)

## References

### Structures

- [decision-removal](../L3_structures/decision-removal.md)

### Terms

- [merge](../L3_terms/merge.md)
- [statement](../L3_terms/statement.md)
- [grounds](../L3_terms/grounds.md)
