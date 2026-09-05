# identifier — 識別子

definition が対象に与えた名前。

- Aliases: 識別子, IDENTIFIER
- Details:
  - 定義されたスコープの外から名指しされているものを、公開された識別子と呼ぶ。
  - 名指しは本体とテストの双方を数える。ドキュメント内の言及は名指しに数えない。
  - 可視性の規則では判定しない。export やアクセス修飾子は言語ごとに増えるため。
  - 公開の深さを属性に持たない。深い識別子は被参照数が多くなり、granularity がそれを持つ。

## Terms
- [definition](../L3_terms/definition.md)
- [granularity](../L3_terms/granularity.md)

## Decisions
- [篩は、定義スコープの外から名指しされていること](../L4_decisions/sieve-is-naming-from-outside.md)
- [公開された識別子の命名は、個別に choice として拾う](../L4_decisions/naming-is-a-choice.md)
