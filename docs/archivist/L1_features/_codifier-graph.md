# codifier-graph — 参照を保つ

<!-- 循環の検査、覆りの処理、近傍図の組み立て -->

## Background

決断は他の決断を根拠にする。参照が循環すると、どれが元でどれが派生かを言えなくなる。

決断は覆る。覆ったものをそのまま消すと何が変わったかが残らず、残すと有効なものに
無効なものが混ざる。覆って消えた決断を指していた側は、存在しないものを指したままになる。

## Availability

- 循環している参照が報告される
    - 報告が出た場合、書き込みは行われない
- 覆った箇所の扱いが指示される
    - 一部が覆ったときは打ち消し線。行は残る
    - 全て覆ったときはファイルごと削除
- 削除された決断を指していた根拠の行が特定される
    - 消えるのは一行だけで、指していた決断は覆らない
- 各決断の近傍図が組み立てられる
    - 出る辺は三ホップ、入る辺は一ホップ
    - 全決断を一枚に描いた図は作られない
- 粒度の順序で参照が制限されない
    - choice が principle を直接指す形は拒否されない

## Decisions
- [参照はグラフであり、循環しない](../L4_decisions/references-form-a-dag.md)
- [覆った内容は打ち消し線で消す](../L4_decisions/overturned-is-struck-through.md)
- [削除された決断への参照は連携して消す](../L4_decisions/cascade-delete-references.md)
- [近傍の参照図は各決断が持つ](../L4_decisions/local-graph-in-each-decision.md)
- [近傍図は出る辺を三ホップ、入る辺を一ホップとする](../L4_decisions/hop-limit-asymmetric.md)
- [スキルは仕事ごとに四つに割る](../L4_decisions/skill-per-job.md)

## References

### Specs

- [graph-maintenance](../L2_specs/graph-maintenance.md)

### Designs

- [codifier-graph](../L2_designs/_codifier-graph.md)
