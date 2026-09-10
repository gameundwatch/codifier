# codifier-escalate — 粒度を上げる

<!-- 被参照数から粒度を決め、上がった分の欄を足す -->

## Background

条項の重さを書いた人の申告で決めると、言ったもの勝ちになる。重いと書いてあることと、
実際に何が拠って立っているかは別のことになる。

拠って立たれている数は数えられる。数えて決めれば、誰が数えても同じ値になる。

## Availability

- 索引から被参照数が数えられ、粒度が決まる
    - 粒度を人が指定することはできない
    - choice / convention / principle の三段
- 閾値を `docs/codifier/config.json` で変えられる
    - 設定が無いときは既定値で動く
- 粒度が上がると理由の欄が足される
    - convention は単一行、principle は複数行
- 粒度は下がらない
    - 参照元が消えて被参照数が減っても、一度上がった段と理由は残る
- 粒度が変わってもファイルは移動しない

## Coverage

| spec | design |
| ---- | ------ |
| [R1](../L2_specs/granularity.md#R1) | [T1](../L2_designs/codifier-escalate.md#T1) |
| [R2](../L2_specs/granularity.md#R2) | [T2](../L2_designs/codifier-escalate.md#T2) |
| [R3](../L2_specs/granularity.md#R3) | [T3](../L2_designs/codifier-escalate.md#T3) |
| [R4](../L2_specs/granularity.md#R4) | [T4](../L2_designs/codifier-escalate.md#T4) |
| [R5](../L2_specs/granularity.md#R5) | [T5](../L2_designs/codifier-escalate.md#T5) |

## Decisions
- [粒度は被参照数で決まる](../L4_decisions/granularity-from-reference-count.md)
- [粒度は choice / convention / principle の三段とする](../L4_decisions/three-granularities.md)
- [粒度が上がるほど記載内容が増える](../L4_decisions/content-grows-with-granularity.md)
- [エスカレーションは不可逆とする](../L4_decisions/escalation-is-irreversible.md)
- [エスカレーションの閾値は利用者が決める](../L4_decisions/thresholds-are-configurable.md)
- [設定は `docs/codifier/config.json` に置く](../L4_decisions/config-in-output-dir.md)
- [スキルは仕事ごとに四つに割る](../L4_decisions/skill-per-job.md)

## References

### Specs

- [granularity](../L2_specs/granularity.md)

### Designs

- [codifier-escalate](../L2_designs/codifier-escalate.md)
