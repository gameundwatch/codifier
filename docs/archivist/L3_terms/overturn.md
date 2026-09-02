# overturn — 覆り

決断が無効になること。

- Aliases: 覆り, OVERTURN
- Details:
  - 覆った箇所は打ち消し線で消す。行は残すため、何が覆ったかを後から読める。
  - ファイルの内容が全て覆ったときは、ノイズを防ぐためファイルごと削除する。
  - 覆ったときは参照グラフを辿り、参照元への影響を検証する。
  - 削除されたとき、それを根拠にしていた決断の根拠欄から参照が消える。

## Terms
- [decision](../L3_terms/decision.md)
- [reference](../L3_terms/reference.md)

## Decisions
- [覆った内容は打ち消し線で消す](../L4_decisions/overturned-is-struck-through.md)
- [削除された決断への参照は連携して消す](../L4_decisions/cascade-delete-references.md)
