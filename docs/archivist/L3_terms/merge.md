# merge — 統合

同じことを言う二枚の決断を一枚にまとめること。

- Aliases: 統合, MERGE
- Details:
  - 先発を残し、後発を消す。先発の判定は索引の timecode 列で行う。
  - 後発を参照していた決断は、参照先を先発へ繋ぎ直す。
  - 先発の被参照数が増えるため、統合がエスカレーションを引き起こすことがある。

## Terms
- [decision](../L3_terms/decision.md)
- [reference](../L3_terms/reference.md)

## Decisions
- [重複は先発に統合する](../L4_decisions/merge-into-the-earlier.md)
- [決断は互いに素である](../L4_decisions/decisions-are-disjoint.md)
- [索引は決断発効時の timecode を持つ](../L4_decisions/index-holds-timecode.md)
