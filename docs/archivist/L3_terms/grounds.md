# grounds — 根拠

その決断が何に拠って立つかを示す欄。

- Aliases: 根拠, GROUNDS
- Details:
  - 根拠にした他の決断への参照と、実装および履歴の指示からなる。
  - 粒度によらず、三段すべてが持つ。
  - ここに置かれた参照の数が、参照先の粒度を決める。
  - 参照先が削除されたとき、その一行は消える。決断そのものは覆らない。

## Terms
- [decision](../L3_terms/decision.md)
- [reference](../L3_terms/reference.md)

## Decisions
- [参照はグラフであり、循環しない](../L4_decisions/references-form-a-dag.md)
- [捨てた案は履歴にしかない](../L4_decisions/decisions-not-in-code.md)
- [粒度が上がるほど記載内容が増える](../L4_decisions/content-grows-with-granularity.md)
- [削除された決断への参照は連携して消す](../L4_decisions/cascade-delete-references.md)
