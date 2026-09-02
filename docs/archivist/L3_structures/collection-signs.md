# collection-signs — 収集の入力と徴候

## Diagrams

<a id="D1"></a>

### D1 入力から復元できるもの

```mermaid
flowchart LR
    C[コード] -->|選んだ案| D[decision]
    H[履歴] -->|捨てた案| D
    C -.->|捨てた案を持たない| X[復元できない]
```

決断は選んだ案と捨てた案の対で成立する。コードは選んだ案しか保存しないため、
コード単体からは復元できない。差戻し・書き換えの前後が捨てた案にあたり、履歴が持つ。
入力が二つあることが、コードだけを読む手法との違いになる。

<a id="D2"></a>

### D2 徴候による判定

```mermaid
flowchart TD
    S[コードと履歴] --> R[反復]
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

徴候は四つで、いずれか一つを持てば決まっているものとして集める。
四つとも持たないものは拾わない。これが人への問い合わせを置き換える篩にあたる。
徴候が増減すれば、この図の行が増減する。

## Decisions
- [徴候から自発的に収集する](../L4_decisions/collect-without-asking.md)
- [決断はコードに無く、履歴にある](../L4_decisions/decisions-not-in-code.md)

## References

### Terms

- [sign](../L3_terms/sign.md)
- [decision](../L3_terms/decision.md)
