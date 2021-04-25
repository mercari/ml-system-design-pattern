# Online AB test pattern

## Usecase
- To confirm the a new prediction model works with the production data.
- To verify a new prediction server can load the production access.
- To test business impact of the model in production.
- To test the model will not worsen the impact than the current one.

## Architecture
The online AB test pattern is an architecture to verity multiple prediction models with the production data and load. In this pattern, you will deploy multiple prediction services parallelly, load balance among them, keeping higher load on the current model, and gradually increase the access to the new server. The load balancing will be managed in the proxy server. The proxy will gather the request data and prediction with identity, and record them in a DWH. You may need to trace the client event log to compare the impact of the new model. The load balancing rule may be considered depending on the objective. If your aim is to compare user activity, it might be better to assign users to a constant model. If your aim is to log the prediction result, you may choose to randomly balance or send request to all the predictions.<br>
If it happens to have problem in prediction, latency or availability, it is better to decide eliminating the new model. You need to consider the term of testing. If the service has seasonal effect, you may need to run longer term, while if the service is used everyday in similar manner, the performance can be concluded in a few week. There may be a chance that you may find the result in shorter term. It is important to decide go or no go based on the effect of the new model replacing the current one.<br>
You will let the new model to be online with responding the prediction to the client. It is important to note that it will affect business or user experience.

## Diagram
![diagram](diagram.png)


## Pros
- You can verity the new model performance without affecting the production service.
- It is possible to record multiple predictions.

## Cons
- It may make a negative impact on your business if the model or server is not good.
- Additional cost

## Needs consideration
- Load balancing policy.
- Evaluation and decision policy of go or no go for the new model.

## Sample
https://github.com/shibuiwilliam/ml-system-in-actions/tree/main/chapter6_operation_management/online_ab_pattern