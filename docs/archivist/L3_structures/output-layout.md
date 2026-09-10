# output-layout — 出力先の配置

## Diagrams

<a id="D1"></a>

### D1 一列の配置

```mermaid
flowchart TD
    R["docs/codifier/"]
    R --> F1[条項ファイル]
    R --> F2[条項ファイル]
    R --> F3[条項ファイル]
    F1 -.- G1[choice]
    F2 -.- G2[convention]
    F3 -.- G3[principle]
```

粒度ごとにディレクトリを分けず、条項を一列に置く。
実線が配置、破線が各ファイルの粒度で、粒度は位置に現れない。
エスカレーションで粒度が変わってもファイルは動かないため、外部からの参照パスが変わらない。
ディレクトリが増えれば、この図に階層が現れる。

## Decisions
- [出力は一列に並べる](../L4_decisions/flat-output-layout.md)
- [出力先は固定する](../L4_decisions/output-path-is-fixed.md)
- [エスカレーションは不可逆とする](../L4_decisions/escalation-is-irreversible.md)

## References

### Terms

- [granularity](../L3_terms/granularity.md)
- [escalation](../L3_terms/escalation.md)
- [choice](../L3_terms/choice.md)
- [convention](../L3_terms/convention.md)
- [principle](../L3_terms/principle.md)
