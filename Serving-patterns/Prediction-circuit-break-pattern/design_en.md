# Prediction circuit break pattern

## Usecase
- When there is a possibility that amount or frequency of request to prediction suddenly increases.
- If it is not applicable to scale out so quick to respond the sudden request.
- If it is not needed to respond 100%.

## Architecture
There are occasions when the number of access to the web service, or related service, suddenly increases due to a campaign or external event. If you are using cloud service or Kubernetes, you can scale out your service to respond the requests, though there are many cases that the increase in amount of request is way beyond the speed of scale out. Especially when the server or container image contains model file, launching or downloading it may take a file.<br>
The prediction circuit breaker pattern is an architecture to avoid `complete outage` until the scale out succeeds. It allows to predict as much as predictable, with cancelling requests more than a certain limit before reaching the prediction server. Thinking that the complete outage is the worst case, you may take into account that a partial outage is rather reasonable. It often happens that with high tide of request that the prediction server restarts which lessens prediction resource. It is reasonable to choose to cancel a certain number of request to stabilize the current prediction service, until the scale out completes to respond all the predictions.<br>
The important point of the pattern is to have a fallback plan for cancelled requests. You have to minimize lowering user experience, and avoid stopping client activity. It is recommended to consider a workflow for cancellation.

## Diagram
![diagram](diagram.png)

## Pros
- Avoid complete outage of the service.
- It allows to scale out prediction servers without lowering the current resource availability.

## Cons
- Require fallback plan for cancelled request.

## Needs consideration
- Fallback plan and workflow for cancellation.
- The circuit breaking limit should be high enough to respond on usual increase in service request.