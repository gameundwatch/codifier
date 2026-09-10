# index — 索引

全条項を一覧する CSV。`docs/codifier/` に一枚だけ置く。

- Aliases: 索引, INDEX
- Details:
  - 列は path・statement・granularity・grounds・timecode の五つ。入次数は grounds 列を数えて得る。
  - timecode は徴候が成立したコミットの時刻。条項ファイルを書いた時刻ではない。
  - timecode は重複を統合するときの先発の判定に使う。
  - 生成物であり、実行のたびに作り直す。手で編集しない。
  - 重複の検出、粒度の算出、循環の検査はここを読んで行う。

## Terms
- [article](../L3_terms/article.md)
- [statement](../L3_terms/statement.md)
- [granularity](../L3_terms/granularity.md)
- [grounds](../L3_terms/grounds.md)

## Decisions
- [索引は CSV で持つ](../L4_decisions/index-is-csv.md)
- [索引は条項発効時の timecode を持つ](../L4_decisions/index-holds-timecode.md)
- [生成された箇所は毎回書き直す](../L4_decisions/generated-parts-are-rewritten.md)
