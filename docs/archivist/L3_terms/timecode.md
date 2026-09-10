# timecode — 発効時刻

条項が効力を持ち始めた時刻。徴候が成立したコミットの時刻を指す。

- Aliases: 発効時刻, TIMECODE
- Details:
  - 粒度によらず、三段すべてが持つ。
  - 条項ファイルを書き出した時刻ではない。同じ範囲を日を変えて集めても同じ値になる。
  - 重複を統合するときの先発の判定に使う。

## Terms
- [article](../L3_terms/article.md)
- [sign](../L3_terms/sign.md)

## Decisions
- [条項は発効時刻を欄として持つ](../L4_decisions/article-holds-timecode.md)
- [索引は条項発効時の timecode を持つ](../L4_decisions/index-holds-timecode.md)
