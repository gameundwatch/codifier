# codifier — 条項を集めて置く

<!-- 四本を呼び、集まった条項を docs/codifier/ に書き出す -->

## Background

実装には判断が積もる。積もった判断は、選ばれた案としてコードに残るだけで、
なぜそうなったかも、他に何を試したかも残らない。ADR を書き始めても、書かれるのは
その後の判断だけで、それ以前に積もった分は取り残される。

集めるだけでは足りない。どこに置くか、どう辿るかが揃っていなければ、集めた条項が
また散る。

## Availability

- 走査範囲を渡して起動すると、その範囲から条項が集まり `docs/codifier/` に並ぶ
    - 収集・互いに素の検査・グラフの保守・昇格の四本を順に呼ぶ
    - 四本はファイルに触れず、書き込みはここが行う
- 条項は粒度によらず一列に置かれる
    - 粒度が上がってもファイルは移動せず、外からの参照が切れない
- 索引 CSV が実行のたびに作り直される
    - 索引を消しても、条項ファイルが揃っていれば同じ内容が戻る
    - 全条項の path・statement・granularity・grounds・timecode が一覧できる
- 各条項が自分の近傍図を持つ
- 人が書いた条項の本文は上書きされない
    - 同名があれば報告して止まる
- 出力先は変更できない

## Decisions
- [書き込みはオーケストレーターが持つ](../L4_decisions/orchestrator-writes.md)
- [スキルは仕事ごとに四つに割る](../L4_decisions/skill-per-job.md)
- [ファイルへの書き込みは一本に集約する](../L4_decisions/single-writer.md)
- [出力先は固定する](../L4_decisions/output-path-is-fixed.md)
- [出力は一列に並べる](../L4_decisions/flat-output-layout.md)
- [索引は CSV で持つ](../L4_decisions/index-is-csv.md)
- [条項は発効時刻を欄として持つ](../L4_decisions/article-holds-timecode.md)
- [生成された箇所は毎回書き直す](../L4_decisions/generated-parts-are-rewritten.md)

## References

### Features

- [codifier-collect](../L1_features/codifier-collect.md)
- [codifier-disjoint](../L1_features/codifier-disjoint.md)
- [codifier-graph](../L1_features/codifier-graph.md)
- [codifier-escalate](../L1_features/codifier-escalate.md)

### Specs

- [output](../L2_specs/output.md)
- [index](../L2_specs/index.md)

### Designs

- [codifier](../L2_designs/codifier.md)
