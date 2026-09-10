# codifier-collect — 収集の設計

## Tasks

<a id="T1"></a>

### T1 履歴側とコード側の走査を別に持つ

- Means: checklist
- 走査範囲を与え、履歴を辿る経路とコードを辿る経路が別々に動き、片方が空でも他方が候補を返すことを見る

<a id="T2"></a>

### T2 四つの徴候それぞれの判定手続き

- Means: checklist
- 反復・収束・差戻し・不動それぞれに当たる履歴を与え、対応する判定だけが成立することを見る

<a id="T3"></a>

### T3 拾わなかったものと理由を戻り値に残す

- Means: checklist
- 徴候を持たない対象を含む範囲を与え、戻り値に不採用の一覧とその理由が並ぶことを見る

<a id="T4"></a>

### T4 走査範囲を最初に確定させ、件数を先に出す

- Means: checklist
- 範囲を伏せたまま呼び、走査の前に範囲を問う応答が返り、確定後に件数が先に出ることを見る

<a id="T5"></a>

### T5 徴候成立と初回名指しのコミットを特定し、時刻を取り出す

- Means: checklist
- 徴候が複数のコミットにまたがる履歴を与え、成立した最後のコミットの時刻が返ることを見る

<a id="T6"></a>

### T6 定義の位置と名前の出現位置を突き合わせ、スコープの外かを判定する

- Means: checklist
- 関数の中の束縛と、外から名指しされる公開識別子を含むコードを与え、後者だけが通ることを見る

<a id="T7"></a>

### T7 同じ対象を指す別綴りを突き合わせ、確定事項に四項を埋める

- Means: checklist
- 同概念の二綴りが双方名指しされているコードを与え、名前・対象・名指し範囲・併存の四項が埋まることを見る

<a id="T8"></a>

### T8 既にある命名の条項を引き当て、改名を覆りとして返す

- Means: checklist
- 命名の条項がある状態で識別子を改名し、戻り値が新規ではなく覆りになることを見る

<a id="T9"></a>

### T9 候補を入口ごとに分けて数えて返す

- Means: checklist
- 両方の入口に候補がある範囲を与え、戻り値の件数が入口ごとに分かれていることを見る

## Parts

| target_name | target_file | IN | OUT |
| ----------- | ----------- | -- | --- |
| codifier-collect | skills/codifier-collect/SKILL.md | 走査範囲, コード, コミット履歴 | 条項の候補（発効時刻つき）と除外一覧 |

### Relation
```mermaid
flowchart LR
    A[範囲を確定] --> B[件数を先に言う]
    B --> H[履歴を走査]
    B --> P[定義を走査]
    H --> D{徴候を持つか}
    D -->|持つ| T[成立したコミットの時刻を取る]
    D -->|持たない| F[除外一覧に理由を残す]
    P --> N{外から名指しされているか}
    N -->|されている| U[初名指しのコミットの時刻を取る]
    N -->|されていない| F
    T --> E[候補に入れる]
    U --> E
    E --> G[入口ごとに件数を分けて返す]
```

## Rules
- 範囲が決まるまで走査しない
    - リポジトリ全体を自らの判断で対象にしない
    - 由来: [徴候から自発的に収集する](../L4_decisions/collect-without-asking.md)
- 走査の途中で人に問わない
    - 判断は徴候の有無だけで行う
    - 由来: [徴候から自発的に収集する](../L4_decisions/collect-without-asking.md)
- コードだけを入力にしない
    - 履歴を読まずに、捨てた案を要する条項を立てない
    - 由来: [捨てた案は履歴にしかない](../L4_decisions/decisions-not-in-code.md)
- 定義を徴候の列に混ぜない
    - 定義側の候補に四つの徴候を要求しない。走査も戻り値も入口ごとに分ける
    - 由来: [定義は徴候ではなく、第二の入口とする](../L4_decisions/definition-is-the-second-entry.md)
- 可視性の規則を判定に使わない
    - 名指しの有無だけで篩う。言語ごとの export 相当を実装が知らないでよい形にする
    - 由来: [篩は、定義スコープの外から名指しされていること](../L4_decisions/sieve-is-naming-from-outside.md)
- 名指しの数え先はコードに限る
    - 本体とテストを数え、ドキュメントを数えない
    - 由来: [篩は、定義スコープの外から名指しされていること](../L4_decisions/sieve-is-naming-from-outside.md)
- 命名を規則へ畳まない
    - 綴りの傾向を見つけても一枚にまとめず、名前ごとに候補を立てる
    - 由来: [公開された識別子の命名は、個別に choice として拾う](../L4_decisions/naming-is-a-choice.md)
- 改名で名前を書き換えない
    - 既にある命名の条項を覆りとして戻す。改名コミットは根拠の実装欄へ回す
    - 由来: [公開識別子の改名は覆りとして扱う](../L4_decisions/rename-is-an-overturn.md)
- 発効時刻は履歴から取る
    - 実行時刻を使わない。二度走らせても同じ値になる
    - 由来: [索引は条項発効時の timecode を持つ](../L4_decisions/index-holds-timecode.md)
- ファイルに書かない
    - 候補を返すだけで、`docs/codifier/` に触れない
    - 由来: [書き込みはオーケストレーターが持つ](../L4_decisions/orchestrator-writes.md)

## Decisions
- [徴候から自発的に収集する](../L4_decisions/collect-without-asking.md)
- [捨てた案は履歴にしかない](../L4_decisions/decisions-not-in-code.md)
- [定義は徴候ではなく、第二の入口とする](../L4_decisions/definition-is-the-second-entry.md)
- [篩は、定義スコープの外から名指しされていること](../L4_decisions/sieve-is-naming-from-outside.md)
- [公開された識別子の命名は、個別に choice として拾う](../L4_decisions/naming-is-a-choice.md)
- [公開識別子の改名は覆りとして扱う](../L4_decisions/rename-is-an-overturn.md)
- [索引は条項発効時の timecode を持つ](../L4_decisions/index-holds-timecode.md)
- [書き込みはオーケストレーターが持つ](../L4_decisions/orchestrator-writes.md)
- [スキルは仕事ごとに四つに割る](../L4_decisions/skill-per-job.md)

## References

### Designs

- [codifier](../L2_designs/codifier.md)

### Structures

- [collection-signs](../L3_structures/collection-signs.md)
- [collection-definition](../L3_structures/collection-definition.md)
- [skill-composition](../L3_structures/skill-composition.md)

### Terms

- [sign](../L3_terms/sign.md)
- [definition](../L3_terms/definition.md)
- [identifier](../L3_terms/identifier.md)
- [decision](../L3_terms/decision.md)
- [index](../L3_terms/index.md)
