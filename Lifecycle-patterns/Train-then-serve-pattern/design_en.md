# Train-then-serve pattern

## Usecase
- To design end-to-end workflow of machine learning model into production.
- When you want to separate training and release into different workflows.
- To manually evaluate model for release quality.
- To evaluate models in production.

## Architecture
When you want to design an architecture and workflow to connect training and serving, you will be combining the training patterns and serving patterns. You can use this train-then-serve pattern, a mixture of multiple patterns, to manually release a trained model after evaluation. Since the workflow includes human tasks, it is not suitable for requirement with frequent model release, but it assures quality of the model and system.<br>
It is possible to use the [model load pattern](../../Operation-patterns/Model-load-pattern/design_en.md) or the [model-in-image pattern](../../Operation-patterns/Model-in-image-pattern/design_en.md) to connect between the training and serving. Criteria of selecting which one depends on how you like to manage model and prediction server. If you want to update the model without change in the current server, you may choose the [model load pattern](../../Operation-patterns/Model-load-pattern/design_en.md), while you need to update the whole server for the [model-in-image pattern](../../Operation-patterns/Model-in-image-pattern/design_en.md).<br>
It is effective to use the [parameter-based serving pattern](../../Operation-patterns/Parameter-based-serving-pattern/design_en.md) for the production serving. It will enable you to update the behaviour of the prediction with modifying an environmental variable in the proxy. For sake of service management, it is mandatory to use the [prediction log pattern](../../Operation-patterns/Prediction-log-pattern/design_en.md) and the [prediction monitoring pattern](../../Operation-patterns/Prediction-monitoring-pattern/design_en.md).<br>
Selecting a serving pattern and QA pattern depends on the production requirement. It will naturally be a combination of patterns. The diagram shows usage of the [web single pattern](../../Serving-patterns/Web-single-pattern/design_en.md) and the [online AB testing pattern](../../QA-patterns/Online-ab-test-pattern/design_en.md). The log will be recorded into a DWH to be used to improve the model and retraining.<br>
An advantage of separating training and serving phases is to evaluate your model before release. If the evaluation based only on your test dataset is not good enough for release, or if manual quality assuarance is required, then this pattern may fit good. In addition, the pattern separates the training and serving phases to isolate issue in the training pipeline from the release and serving system, that strengthens service availability. On the other hand, it is not suitable for usecase where you need to update the model realtime or frequently.


## Diagram
![diagram](diagram.png)


## Pros
- Manual model evaluation before release.
- Isolate workflow and failure in each phase.

## Cons
- Not automated.

## Needs consideration
- Combination of training, QA, operation and serving patterns.
- Release standard.
- Release frequency.