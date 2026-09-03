# codifier-collect — 決断を集める

<!-- コードと履歴から、決まっていることを徴候で拾う -->

## Background

コードは選ばれた案しか保存しない。捨てた案と、それを捨てた経緯は履歴にある。
コードだけを読んで設計や要件が分かるという通説は、選ばれた案を読めることを
指しているに過ぎない。

決まっているかどうかを人に聞いて回ると、既存の実装に対しては終わらない。
決まっている証拠は履歴の側にある。

## Availability

- 走査範囲を渡すと、その範囲のコードと履歴から決断の候補が挙がる
    - 範囲が決まるまで走査は始まらない
    - 件数が先に示される
- 徴候を持つものだけが挙がる
    - 反復・収束・差戻し・不動の四つ
    - いずれか一つを持てば挙がる
- 挙がらなかったものが理由つきで残る
- 途中で問い合わせが来ない
- 候補には徴候が成立したコミットの時刻が付く
    - 同じリポジトリを日を変えて集めても同じ値になる

## Decisions
- [徴候から自発的に収集する](../L4_decisions/collect-without-asking.md)
- [決断はコードに無く、履歴にある](../L4_decisions/decisions-not-in-code.md)
- [索引は決断発効時の timecode を持つ](../L4_decisions/index-holds-timecode.md)
- [スキルは仕事ごとに四つに割る](../L4_decisions/skill-per-job.md)

## References

### Specs

- [collection](../L2_specs/collection.md)

### Designs

- [codifier-collect](../L2_designs/_codifier-collect.md)
