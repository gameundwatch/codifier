# neighborhood — 近傍

一つの条項から辿れる範囲のうち、その条項のファイルに図として描かれる部分。

- Aliases: 近傍, NEIGHBORHOOD
- Details:
  - 出る辺は三ホップ、入る辺は一ホップまで。
  - 全体を一枚に描いた図は置かないため、図はここにしか無い。
  - 生成物であり、実行のたびに作り直す。手で書かない。

## Terms
- [reference](../L3_terms/reference.md)
- [article](../L3_terms/article.md)

## Decisions
- [近傍の参照図は各条項が持つ](../L4_decisions/local-graph-in-each-article.md)
- [近傍図は出る辺を三ホップ、入る辺を一ホップとする](../L4_decisions/hop-limit-asymmetric.md)
- [生成された箇所は毎回書き直す](../L4_decisions/generated-parts-are-rewritten.md)
