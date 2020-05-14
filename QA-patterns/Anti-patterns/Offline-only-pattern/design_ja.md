# Offline only pattern

## Case
- 機械学習のモデルをオフラインのテストデータでしか評価していない状態。

## Situation
機械学習のモデルがビジネス的な価値を発揮するのは本番システムに組み込まれ、事業や効率化に貢献するときです。モデルが有用かどうか判断するのは事業や効率化の効果であって、テストデータではありません。テストデータはモデルをリリース可能かどうか判断する指標の一つにはなりますが、ビジネス上の評価にはなりません。テストデータで99.99%の正解率を得ていても、オンラインの実データで効果を発揮できないのであれば（または悪影響を及ぼすのであれば）、モデルは不要でしょう。推論器としてリリースしたモデルは実用の中で効果検証する必要があります。もしモデルがビジネスに悪影響を与え続けているようであれば、まずはモデルへのリクエストを停止して、モデルを使っていなかったときの状態に戻すことを推奨します（[Parameter-based serving pattern](../../../Operation-patterns/Parameter-based-serving-pattern/design_ja.md)を使うと簡単に切り戻すことができます）。

## Diagram
![diagram](diagram.png)


## Pros
- 特になし。

## Cons
- 推論器を本来の指標で評価できない。

## Work around
- モデルをリリースすることで得られる効果を定量的に定義し、リリース前とリリース後（またはA/BテストのA郡とB郡）を分割し、評価に必要なログを設計、収集し、一定期間後に効果検証を行い、推論器の維持または停止を判断する。

## Related design pattern
- [Shadow AB-testing pattern](./../../Shadow-ab-test-pattern/design_ja.md)
- [Online AB-testing pattern](./../../Online-ab-test-pattern/design_ja.md)