# decision — 決断

決めたこと。codifier が集める単位であり、他の層の文書はすべてここから起こされる。

- Aliases: 決断, DECISION
- Details:
  - 互いに素である。同じことを二枚が言わない。参照関係を持つことはこれを妨げない。
  - 粒度と参照を属性として持つ。種別は持たない。
  - 一枚ごとに自分の近傍図を持つ。全決断の一覧は索引が持つ。
  - statement・timecode・grounds を粒度によらず持ち、粒度に応じて rationale を加える。
  - 捨てた案を要するものは、選んだ案と捨てた案の対で成立し、捨てた案は履歴が持つ。
  - definition のように、捨てた案を持たずに成立するものもある。
  - 重複したときは先発へ統合される。覆ったときは打ち消し線で消し、全て覆れば削除される。

## Decisions
- [決断は互いに素である](../L4_decisions/decisions-are-disjoint.md)
- [捨てた案は履歴にしかない](../L4_decisions/decisions-not-in-code.md)
- [重複は先発に統合する](../L4_decisions/merge-into-the-earlier.md)
- [覆った内容は打ち消し線で消す](../L4_decisions/overturned-is-struck-through.md)
- [決断は種別を持たない](../L4_decisions/no-kind-attribute.md)
- [近傍の参照図は各決断が持つ](../L4_decisions/local-graph-in-each-decision.md)
- [決断は発効時刻を欄として持つ](../L4_decisions/decision-holds-timecode.md)
