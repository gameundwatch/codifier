# merge — 統合

同じことを言う二枚の条項を一枚にまとめること。

- Aliases: 統合, MERGE
- Details:
  - 先発を残し、後発を消す。先発の判定は索引の timecode 列で行う。
  - 後発を参照していた条項は、参照先を先発へ繋ぎ直す。
  - 先発の被参照数が増えるため、統合がエスカレーションを引き起こすことがある。

## Terms
- [article](../L3_terms/article.md)
- [reference](../L3_terms/reference.md)

## Decisions
- [重複は先発に統合する](../L4_decisions/merge-into-the-earlier.md)
- [条項は互いに素である](../L4_decisions/articles-are-disjoint.md)
- [索引は条項発効時の timecode を持つ](../L4_decisions/index-holds-timecode.md)
