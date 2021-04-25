# Parameter-based serving pattern

## Usecase
- To control prediction with parameter.
- When it is possible to control rule-based.

## Architecture
In general it is impossible to edit parameters in a trained model. On the other hand, a model may not always align with business logic or system requirement. For instance, if the model in production is giving negative effect on your business for some reason, you may need to update the model, or remove the prediction from the service. If it takes long to retrain the model and build it to production use, possibly you need to decide to remove the prediction temporalily. Or, there may be a chance that your prediction is anomaly only for a certain input data, and all the others are right. In that case, you still need to either retrain the model, or eliminate prediction for that particular kind of data. When you need to implement a machine learning prediction into a productiono service, it is not always the case that high accuracy results in good business impact, and you may need to consider an edge case or systematic issue, which may need to be mitigated in some rule-based ways.<br>
For those cases, it is useful to add a mechanism in your code to change behaviour of all or a part of the predictions, including stopping, retrying or timeout. You may use arguments to specify with execution command to control the change, or use environmental variables for container native application. Since it is difficult to keep high accuracy without any error for a model for every case or every input data, it is better to estimate possible anomaly and control with rulebased mechanism. On the other hand, it is impossible to cover all the abnormals. It may be good to have a `Activate` or not variable to just stop all the predictions to prevent worst case.


## Diagram
![diagram](diagram.png)


## Pros
- To avoid abnormal prediction for edge cases.

## Cons
- Impossible to cover all the cases.
- Increase in rules make complexity in operation.

## Needs consideration
- Which cases to control with what variable.

## Sample
https://github.com/shibuiwilliam/ml-system-in-actions/tree/main/chapter6_operation_management/paramater_based_pattern