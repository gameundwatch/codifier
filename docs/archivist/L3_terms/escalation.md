# escalation — エスカレーション

被参照数が閾値を超えて、決断の粒度が上がること。

- Aliases: エスカレーション, ESCALATION
- Details:
  - 不可逆。参照元が覆されて被参照数が減っても、粒度は下がらない。
  - 閾値は利用者が決める。既定値は出発点であって規則ではない。
  - 粒度が上がるため、書く内容が増える方向にしか変わらない。

## Terms
- [granularity](../L3_terms/granularity.md)
- [reference](../L3_terms/reference.md)

## Decisions
- [エスカレーションは不可逆とする](../L4_decisions/escalation-is-irreversible.md)
- [エスカレーションの閾値は利用者が決める](../L4_decisions/thresholds-are-configurable.md)
- [粒度が上がるほど記載内容が増える](../L4_decisions/content-grows-with-granularity.md)
