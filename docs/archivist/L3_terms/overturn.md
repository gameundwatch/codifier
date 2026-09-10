# overturn — 覆り

条項が無効になること。

- Aliases: 覆り, OVERTURN
- Details:
  - 覆った箇所は打ち消し線で消す。行は残すため、何が覆ったかを後から読める。
  - ファイルの内容が全て覆ったときは、ノイズを防ぐためファイルごと削除する。
  - 覆ったときは参照グラフを辿り、参照元への影響を検証する。
  - 削除されたとき、それを根拠にしていた条項の根拠欄から参照が消える。

## Terms
- [article](../L3_terms/article.md)
- [reference](../L3_terms/reference.md)

## Decisions
- [覆った内容は打ち消し線で消す](../L4_decisions/overturned-is-struck-through.md)
- [削除された条項への参照は連携して消す](../L4_decisions/cascade-delete-references.md)
