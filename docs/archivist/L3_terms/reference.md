# reference — 参照

ある決断が別の決断を根拠として指すこと。

- Aliases: 参照, REFERENCE
- Details:
  - 参照の全体は有向非巡回グラフになる。木ではない。
  - 層構造を成さない。粒度の小さい決断が大きい決断を直接参照してよい。
  - 入ってくる参照の数が粒度を決める。

## Terms
- [decision](../L3_terms/decision.md)

## Decisions
- [参照はグラフであり、循環しない](../L4_decisions/references-form-a-dag.md)
- [粒度は被参照数で決まる](../L4_decisions/granularity-from-reference-count.md)
