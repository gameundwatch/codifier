# decision — 決断

決めたこと。codifier が集める単位であり、他の層の文書はすべてここから起こされる。

- Aliases: 決断, DECISION
- Details:
  - 互いに素である。同じことを二枚が言わない。参照関係を持つことはこれを妨げない。
  - 粒度・種別・参照を属性として持つ。
  - コードには無い。選んだ案と捨てた案の対で成立し、捨てた案は履歴が持つ。
  - 重複したときは先発へ統合される。覆ったときは打ち消し線で消し、全て覆れば削除される。

## Decisions
- [決断は互いに素である](../L4_decisions/decisions-are-disjoint.md)
- [決断はコードに無く、履歴にある](../L4_decisions/decisions-not-in-code.md)
- [重複は先発に統合する](../L4_decisions/merge-into-the-earlier.md)
- [覆った内容は打ち消し線で消す](../L4_decisions/overturned-is-struck-through.md)
