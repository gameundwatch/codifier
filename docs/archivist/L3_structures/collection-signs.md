# collection-signs — 収集の入口と徴候

## Diagrams

<a id="D1"></a>

### D1 二つの入口

```mermaid
flowchart LR
    H[履歴] -->|捨てた案を持つ| S[sign]
    C[コード] -->|捨てた案を持たない| F[definition]
    S --> D[decision]
    F --> D
```

入口は二つある。履歴の入口は捨てた案を持ち、定義の入口は持たない。
捨てた案を要する決断はコード単体からは復元できないが、コードが指している決断の写像は
書ける。定義のように、捨てた案を持たずに成立する決断があるため。
入口が増減すれば、この図の行が増減する。

<a id="D2"></a>

### D2 徴候による判定

```mermaid
flowchart TD
    S[履歴] --> R[反復]
    S --> V[収束]
    S --> B[差戻し]
    S --> F[不動]
    R --> Y[決まっている]
    V --> Y
    B --> Y
    F --> Y
    S --> N[徴候なし] --> Z[拾わない]
    Y --> G[decision として集める]
```

徴候は履歴から判定する。四つで、いずれか一つを持てば決まっているものとして集める。
四つとも持たないものは拾わない。これが人への問い合わせを置き換える篩にあたる。
徴候は四つのままとし、増やさない。定義はこの列に並ばず、第二の入口として立つ。
定義の入口の篩は [collection-definition](../L3_structures/collection-definition.md) が持つ。

## Decisions
- [徴候から自発的に収集する](../L4_decisions/collect-without-asking.md)
- [捨てた案は履歴にしかない](../L4_decisions/decisions-not-in-code.md)
- [定義は徴候ではなく、第二の入口とする](../L4_decisions/definition-is-the-second-entry.md)

## References

### Structures

- [collection-definition](../L3_structures/collection-definition.md)

### Terms

- [sign](../L3_terms/sign.md)
- [definition](../L3_terms/definition.md)
- [decision](../L3_terms/decision.md)
