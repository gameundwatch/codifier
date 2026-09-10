# codifier-escalate — 昇格の設計

## Tasks

<a id="T1"></a>

### T1 索引の grounds 列を横断して入次数を数える

- Means: checklist
- 同じ条項を grounds に挙げる行を複数置き、その条項の入次数がその件数に一致することを見る

<a id="T2"></a>

### T2 入次数を三段のいずれかへ写す

- Means: checklist
- 閾値の前後の入次数を与え、choice / convention / principle の境で段が切り替わることを見る

<a id="T3"></a>

### T3 段が上がったとき rationale の欄だけを足す

- Means: checklist
- 段が上がる条項を与え、rationale が足され、他の欄が変わらないことを見る

<a id="T4"></a>

### T4 現在の粒度と算出値を比べ、大きい側を採る

- Means: checklist
- 算出値が現在より小さい条項を与え、粒度が下がらないことを見る

<a id="T5"></a>

### T5 `config.json` を読み、欠けたときは既定値を使う

- Means: checklist
- 閾値を書いた config.json がある場合と無い場合の両方で呼び、前者が優先され後者が既定値で動くことを見る

## Parts

| target_name | target_file | IN | OUT |
| ----------- | ----------- | -- | --- |
| codifier-escalate | skills/codifier-escalate/SKILL.md | 索引, 確定した集合, 設定 | 粒度の変更と欄の追加の指示 |

### Relation
```mermaid
flowchart LR
    I[(索引)] --> D[入次数を数える]
    C[config.json] --> T[閾値を読む]
    D --> J[段を決める]
    T --> J
    J --> M["現在の段と比べて大きい側を採る"]
    M -->|上がった| A[rationale の欄を足す指示]
    M -->|据え置き| N[何もしない]
```

## Rules
- 降格しない
    - 算出値が現在より小さくても、粒度を下げる指示を出さない
    - 由来: [エスカレーションは不可逆とする](../L4_decisions/escalation-is-irreversible.md)
- 粒度を人が指定できない
    - 入次数と閾値の外から粒度を受け取らない
    - 由来: [粒度は被参照数で決まる](../L4_decisions/granularity-from-reference-count.md)
- 閾値は設定から読む
    - 設定が無いときだけ既定値を使い、既定値を規則として扱わない
    - 由来: [エスカレーションの閾値は利用者が決める](../L4_decisions/thresholds-are-configurable.md)
- 設定は出力先の中から読む
    - `docs/codifier/config.json` 以外の場所を探さない
    - 利用者が置くファイルなので Parts に挙げない。無いときは既定値で動く
    - 由来: [設定は `docs/codifier/config.json` に置く](../L4_decisions/config-in-output-dir.md)
- ファイルを移動させない
    - 段が上がっても、欄を足すだけでパスを変えない
    - 由来: [出力は一列に並べる](../L4_decisions/flat-output-layout.md)
- ファイルに書かない
    - 指示を返すだけで、欄の追加そのものは行わない
    - 由来: [書き込みはオーケストレーターが持つ](../L4_decisions/orchestrator-writes.md)

## Decisions
- [粒度は被参照数で決まる](../L4_decisions/granularity-from-reference-count.md)
- [粒度は choice / convention / principle の三段とする](../L4_decisions/three-granularities.md)
- [粒度が上がるほど記載内容が増える](../L4_decisions/content-grows-with-granularity.md)
- [エスカレーションは不可逆とする](../L4_decisions/escalation-is-irreversible.md)
- [エスカレーションの閾値は利用者が決める](../L4_decisions/thresholds-are-configurable.md)
- [設定は `docs/codifier/config.json` に置く](../L4_decisions/config-in-output-dir.md)
- [Parts に自動生成物を挙げない](../L4_decisions/parts-exclude-generated.md)
- [出力は一列に並べる](../L4_decisions/flat-output-layout.md)
- [書き込みはオーケストレーターが持つ](../L4_decisions/orchestrator-writes.md)

## References

### Designs

- [codifier](../L2_designs/codifier.md)

### Structures

- [granularity-ladder](../L3_structures/granularity-ladder.md)
- [configurable-surface](../L3_structures/configurable-surface.md)
- [index-format](../L3_structures/index-format.md)

### Terms

- [escalation](../L3_terms/escalation.md)
- [granularity](../L3_terms/granularity.md)
- [rationale](../L3_terms/rationale.md)
- [index](../L3_terms/index.md)
