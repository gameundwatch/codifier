# codifier-disjoint — 重複を見つけて統合する

<!-- 同じことを言う条項を検出し、先発への統合を指示する -->

## Background

同じことを二枚が言っていると、片方を覆したときにもう片方が生き残る。どちらが
効いているのかが読み手に判定できなくなり、条項の集まりが判断の材料にならなくなる。

参照関係があるだけの組は重複ではない。区別できないと、根拠を持つ条項が
片端から統合されてしまう。

## Availability

- 索引と新しい候補を渡すと、同じことを言っている組が報告される
    - 比較は statement の内容で行われる
    - 一方が他方を根拠にしているだけの組は報告されない
- 統合の向きは常に先発
    - どちらが先発かは索引の timecode で決まる
    - 後発だけが持っていた根拠は先発へ移る
- 後発を指していた根拠が先発へ繋ぎ直される
    - 先発の被参照数が増え、昇格の対象になることがある

## Decisions
- [条項は互いに素である](../L4_decisions/articles-are-disjoint.md)
- [重複は先発に統合する](../L4_decisions/merge-into-the-earlier.md)
- [索引は条項発効時の timecode を持つ](../L4_decisions/index-holds-timecode.md)
- [スキルは仕事ごとに四つに割る](../L4_decisions/skill-per-job.md)

## References

### Specs

- [disjointness](../L2_specs/disjointness.md)

### Designs

- [codifier-disjoint](../L2_designs/codifier-disjoint.md)
