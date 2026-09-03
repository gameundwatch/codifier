# codifier — オーケストレーターの設計

## Needs

| spec | needs |
| ---- | ----- |
| [R1](../L2_specs/output.md#R1) | 出力先を定数として一箇所に持ち、外から差し替える口を作らない |
| [R2](../L2_specs/output.md#R2) | 決断本文と生成物で書き込みの扱いを分ける分岐 |
| [R3](../L2_specs/output.md#R3) | ファイル名を粒度から独立に決める規則 |
| [R4](../L2_specs/output.md#R4) | 四本の戻り値を受け取る形。四本にファイル操作を持たせない |
| [R1](../L2_specs/index.md#R1) | CSV の直列化と、引用符を含む値の扱い |
| [R2](../L2_specs/index.md#R2) | 決断ファイルの一覧と索引の行を突き合わせる手順 |
| [R4](../L2_specs/index.md#R4) | 索引を実行の最後に作り直す順序 |

## Parts

| target_name | target_file | IN | OUT |
| ----------- | ----------- | -- | --- |
| codifier | skills/codifier/SKILL.md | 四本の戻り値 | docs/codifier/ |
| 決断の書式 | skills/codifier/TEMPLATE.md | - | 決断ファイル |
| 索引 | docs/codifier/index.csv | 決断ファイル群 | - |

### Relation
```mermaid
flowchart LR
    O[codifier] --> C1[四本を呼ぶ]
    C1 --> C2[戻り値を受け取る]
    C2 --> C3[決断ファイルを書く]
    C3 --> C4[索引を作り直す]
    C4 --> C5[近傍図を作り直す]
```

## Rules
- 四本はファイルに触れない
    - 戻り値は書く内容であって、書き込みではない
    - 由来: [書き込みはオーケストレーターが持つ](../L4_decisions/orchestrator-writes.md)
- timecode は打たずに受け取る
    - 収集が返した発効時刻をそのまま索引へ載せる。書き込み時刻を使わない
    - 由来: [索引は決断発効時の timecode を持つ](../L4_decisions/index-holds-timecode.md)
- 生成物は毎回作り直す
    - 索引と近傍図は実行の末尾でまとめて再生成する
    - 由来: [生成された箇所は毎回書き直す](../L4_decisions/generated-parts-are-rewritten.md)
- 人が書いた決断本文は上書きしない
    - 同名があれば報告して止める
    - 由来: [出力先は固定する](../L4_decisions/output-path-is-fixed.md)
- ファイル名に粒度を含めない
    - 粒度が変わってもパスが変わらないため
    - 由来: [出力は一列に並べる](../L4_decisions/flat-output-layout.md)

## Decisions
- [書き込みはオーケストレーターが持つ](../L4_decisions/orchestrator-writes.md)
- [ファイルへの書き込みは一本に集約する](../L4_decisions/single-writer.md)
- [索引は CSV で持つ](../L4_decisions/index-is-csv.md)
- [索引は決断発効時の timecode を持つ](../L4_decisions/index-holds-timecode.md)
- [生成された箇所は毎回書き直す](../L4_decisions/generated-parts-are-rewritten.md)
- [出力先は固定する](../L4_decisions/output-path-is-fixed.md)
- [出力は一列に並べる](../L4_decisions/flat-output-layout.md)

## References

### Structures

- [skill-composition](../L3_structures/skill-composition.md)
- [writing-path](../L3_structures/writing-path.md)
- [index-format](../L3_structures/index-format.md)

### Terms

- [index](../L3_terms/index.md)
- [neighborhood](../L3_terms/neighborhood.md)
- [decision](../L3_terms/decision.md)
