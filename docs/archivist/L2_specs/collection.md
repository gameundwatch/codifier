# collection — 決断を集める要件

## Requirements

<a id="R1"></a>

### R1 入力はコードと履歴の両方とする

- 履歴を読まずにコードだけを入力にしない
- 差戻し、書き換えの前後、収束した変更列を捨てた案として読む

<a id="R2"></a>

### R2 徴候を持つものだけを集める

- 徴候は反復・収束・差戻し・不動の四つ
- いずれか一つを持てば集める

<a id="R3"></a>

### R3 徴候を持たないものは集めない

- 一度きりの変更、揺れ続けている箇所は対象外
- 対象外にした理由を報告に残す

<a id="R4"></a>

### R4 一件ずつ人に問い合わせない

- 収集の途中で判断を人に委ねない
- 走査の範囲は開始前に人が決める

## Verify

| No | VERIFY_NAME | REQUIREMENT |
| -- | ----------- | ----------- |
| 1 | [履歴が入力に入る](#V1) | [R1](#R1) |
| 2 | [徴候による採用](#V2) | [R2](#R2) |
| 3 | [徴候なしの除外](#V3) | [R3](#R3) |
| 4 | [問い合わせの不在](#V4) | [R4](#R4) |

<a id="V1"></a>

### V1 履歴が入力に入る

- Means: checklist
- 同じ最終状態で履歴の異なる二つのリポジトリを与え、集まる決断が異なることを見る

<a id="V2"></a>

### V2 徴候による採用

- Means: checklist
- 四つの徴候それぞれを一つだけ持つ変更を与え、いずれも決断として集まることを見る

<a id="V3"></a>

### V3 徴候なしの除外

- Means: checklist
- 一度きりの変更だけを含むリポジトリを与え、決断が生成されないことを見る

<a id="V4"></a>

### V4 問い合わせの不在

- Means: checklist
- 範囲を与えた後、完了までに人への問いが発生しないことを見る

## Decisions
- [徴候から自発的に収集する](../L4_decisions/collect-without-asking.md)
- [決断はコードに無く、履歴にある](../L4_decisions/decisions-not-in-code.md)

## References

### Structures

- [collection-signs](../L3_structures/collection-signs.md)

### Terms

- [sign](../L3_terms/sign.md)
- [decision](../L3_terms/decision.md)
