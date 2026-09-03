# timecode — 発効時刻

決断が効力を持ち始めた時刻。徴候が成立したコミットの時刻を指す。

- Aliases: 発効時刻, TIMECODE
- Details:
  - 粒度によらず、三段すべてが持つ。
  - 決断ファイルを書き出した時刻ではない。同じ範囲を日を変えて集めても同じ値になる。
  - 重複を統合するときの先発の判定に使う。

## Terms
- [decision](../L3_terms/decision.md)
- [sign](../L3_terms/sign.md)

## Decisions
- [決断は発効時刻を欄として持つ](../L4_decisions/decision-holds-timecode.md)
- [索引は決断発効時の timecode を持つ](../L4_decisions/index-holds-timecode.md)
