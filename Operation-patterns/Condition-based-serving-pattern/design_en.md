# Condition-based serving pattern

## Usecase
- When prediction target varies a lot by condition.
- When you can conditionally select a model in rule-based manner.

## Architecture
The condition-based serving pattern is an architecture to select a model based on condition. You may have a situation where the prediction target varies depending on an user's condition, like time, place and persona. Say, you made a machine learning model to recommend a menu to your client. Recommending steak or wine for morning time is probably not adequate. Say, you made a camera-based product to classify a landmark building. There is very low probability that you classify a bridge in Japan as Golden Gate Bridge located in California. It is possible to separate target variables based on condition you run the prediction.<br>
You need to develop a prediciton service for each condition. The selection and distribution to each model will be controled in a proxy. The selection rule may depend on usecase: if you need to select based on time, you may need a morning model for morning, a noon model for noon, and a night model for night time. Difficulty of model development depends on how the problem space and target variable change with conditional change. If it is possible to share a feature engineering of one model with others, you may only need to update target variable for each condition. If the condition varies drastically that makes impossible to share, then you have to make independent models, or you may have not to choose this pattern. Since you will need to develop an overfitted model for each condition in the pattern, you may expect the model to predict better than a general model.<br>
If the number of models become too large, the amount of work you need for the model evaluation, improvement and management will increase that you may need to reconsider choosing the pattern in balance with cost is the right choice for your problem solving.<br>
Separating the condition depends on how the model input, feature and target vary. There may be a chance that you use a same model for morning and night time. On the other hand, it may cause an operational mistake if you make a conditional separation way different from person's understanding of condition.

## Diagram
![diagram](diagram.png)


## Pros
- Select an adequate model depending on condition.

## Cons
- Operational cost raise with number of models.

## Needs consideration
- How to separate condition.
- Balance between number of models and model management.

## Sample
https://github.com/shibuiwilliam/ml-system-in-actions/tree/main/chapter6_operation_management/condition_based_pattern