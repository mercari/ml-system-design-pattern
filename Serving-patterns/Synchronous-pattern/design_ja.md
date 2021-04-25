# Synchronous pattern

## Usecase
- アプリケーションのワークフローとして、推論結果が出るまで次に進めない仕様のとき
- ワークフローが推論結果に依存するとき

## Architecture
同期パターンは機械学習の推論を同期的に処理するパターンです。クライアントは推論のリクエストに対してレスポンスが得られるまで待機します。機械学習の推論サーバをRESTまたはGRPCで構成した場合、同期パターンになることが多いです。推論含めたワークフローを考えやすいため、同期パターンは実装・運用しやすいアーキテクチャになります。

## Diagram
![diagram](diagram.png)

## Pros
- シンプルな構成で運用しやすい。
- 推論が完了するまでクライアントは次の処理に移行しないため、ワークフローを考えやすい。

## Cons
- 推論がパフォーマンスのボトルネックになりやすい。
- 推論の待機時間が発生するため、その間にユーザ体験を低下させない方法を考慮する必要がある。

## Needs consideration
- 推論の待機時間に対するユーザ体験の低下防止。
- 待機時間が長い場合はクライアントからタイムアウトすることが必要になる場合もある。

## Sample
https://github.com/shibuiwilliam/ml-system-in-actions/tree/main/chapter4_serving_patterns/synchronous_pattern
