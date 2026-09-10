# article — 条項

codifier が集める単位。他の層の文書はすべてここから起こされる。

- Aliases: 条項, ARTICLE
- Details:
  - decision と definition の二種からなる。捨てた案を持つか否かで分かれる。
  - 互いに素である。同じことを二枚が言わない。参照関係を持つことはこれを妨げない。
  - 粒度と参照を属性として持つ。種別は持たない。
  - 一枚ごとに自分の近傍図を持つ。全条項の一覧は索引が持つ。
  - statement・timecode・grounds を粒度によらず持ち、粒度に応じて rationale を加える。
  - 重複したときは先発へ統合される。覆ったときは打ち消し線で消し、全て覆れば削除される。

## Decisions
- [集める単位は条項とし、decision と definition に分ける](../L4_decisions/article-is-the-collected-unit.md)
- [条項は互いに素である](../L4_decisions/articles-are-disjoint.md)
- [重複は先発に統合する](../L4_decisions/merge-into-the-earlier.md)
- [覆った内容は打ち消し線で消す](../L4_decisions/overturned-is-struck-through.md)
- [条項は種別を持たない](../L4_decisions/no-kind-attribute.md)
- [近傍の参照図は各条項が持つ](../L4_decisions/local-graph-in-each-article.md)
- [条項は発効時刻を欄として持つ](../L4_decisions/article-holds-timecode.md)
