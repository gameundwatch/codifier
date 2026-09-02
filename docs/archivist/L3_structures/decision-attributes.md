# decision-attributes — 決断が持つ属性

## Diagrams

<a id="D1"></a>

### D1 決断の三属性

```mermaid
flowchart TD
    D[decision]
    D --> G[granularity]
    D --> R[reference]
    G --> G1[choice]
    G --> G2[convention]
    G --> G3[principle]
    R --> D2[別の decision]
```

決断は粒度と参照の二つを持つ。種別を持たないのは、他の案を試した跡が grounds から
読めるためで、欄にすると写しになる。
参照だけが他の決断を指し、粒度は決断自身の属性で閉じる。
属性が二つより増えることは、この図に行が増えることで分かる。

## Decisions
- [決断は種別を持たない](../L4_decisions/no-kind-attribute.md)
- [決断は互いに素である](../L4_decisions/decisions-are-disjoint.md)
- [粒度は choice / convention / principle の三段とする](../L4_decisions/three-granularities.md)

## References

### Terms

- [decision](../L3_terms/decision.md)
- [granularity](../L3_terms/granularity.md)
- [reference](../L3_terms/reference.md)
- [grounds](../L3_terms/grounds.md)
