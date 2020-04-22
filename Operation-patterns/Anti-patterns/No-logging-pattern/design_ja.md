# No logging pattern

## Case
- ログやプロファイルを取得していない状態。

## Situation
機械学習システムに限らず、システムを運用するためにはログが必要です。ログを取得しない場合、エラー検知や障害対応、システム改善を行うことができず、ブラックボックスなシステムが醸成されていきます。特に機械学習システムでは、推論結果とその後のイベントをログから追跡することによって、推論モデルの効果をレビューすることが可能になります。

## Diagram
![diagram](diagram.png)


## Pros
- 強いて言えば、ログの費用が不要になる。

## Cons
- システムを運用することができなくなる。

## Work around
- 最低限、Fatal、Error、Warning、Infoレベルのログは取得する。
- 追跡可能なイベントログを定義し実装する。

## Related design pattern
- [Prediction log pattern](./../../Prediction-log-pattern/design_ja.md)
- [Prediction monitoring pattern](./../../Prediction-monitoring-pattern/design_ja.md)