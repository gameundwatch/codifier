# codifier-graph — 参照を保つ

<!-- 循環の検査、覆りの処理、近傍図の組み立て -->

## Background

条項は他の条項を根拠にする。参照が循環すると、どれが元でどれが派生かを言えなくなる。

条項は覆る。覆ったものをそのまま消すと何が変わったかが残らず、残すと有効なものに
無効なものが混ざる。覆って消えた条項を指していた側は、存在しないものを指したままになる。

## Availability

- 循環している参照が報告される
    - 報告が出た場合、書き込みは行われない
- 覆った箇所の扱いが指示される
    - 一部が覆ったときは打ち消し線。行は残る
    - 全て覆ったときはファイルごと削除
- 削除された条項を指していた根拠の行が特定される
    - 消えるのは一行だけで、指していた条項は覆らない
- 各条項の近傍図が組み立てられる
    - 出る辺は三ホップ、入る辺は一ホップ
    - 全条項を一枚に描いた図は作られない
- 粒度の順序で参照が制限されない
    - choice が principle を直接指す形は拒否されない

## Coverage

| spec | design |
| ---- | ------ |
| [R1](../L2_specs/graph-maintenance.md#R1) | [T1](../L2_designs/codifier-graph.md#T1) |
| [R2](../L2_specs/graph-maintenance.md#R2) | [T2](../L2_designs/codifier-graph.md#T2) |
| [R3](../L2_specs/graph-maintenance.md#R3) | [T3](../L2_designs/codifier-graph.md#T3) |
| [R4](../L2_specs/graph-maintenance.md#R4) | [T4](../L2_designs/codifier-graph.md#T4) |
| [R5](../L2_specs/graph-maintenance.md#R5) | [T5](../L2_designs/codifier-graph.md#T5) |

## Decisions
- [参照はグラフであり、循環しない](../L4_decisions/references-form-a-dag.md)
- [覆った内容は打ち消し線で消す](../L4_decisions/overturned-is-struck-through.md)
- [削除された条項への参照は連携して消す](../L4_decisions/cascade-delete-references.md)
- [近傍の参照図は各条項が持つ](../L4_decisions/local-graph-in-each-article.md)
- [近傍図は出る辺を三ホップ、入る辺を一ホップとする](../L4_decisions/hop-limit-asymmetric.md)
- [スキルは仕事ごとに四つに割る](../L4_decisions/skill-per-job.md)

## References

### Specs

- [graph-maintenance](../L2_specs/graph-maintenance.md)

### Designs

- [codifier-graph](../L2_designs/codifier-graph.md)
