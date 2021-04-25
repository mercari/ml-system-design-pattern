# Synchronous pattern

## Usecase
- When in your business logic, the model inference is a blocker to proceed to the next step.
- When your workflow depends on the inference result.

## Architecture
The synchronous pattern is used to run prediction synchronously. It blocks the workflow until the prediction finishes. If you develop the inference server with REST or GRPC, it often becomes the synchronous pattern. This is one of the easiest patterns to use, as its workflow can be visualized in a simple step-by-step fashion.

## Diagram
![diagram](diagram.png)

## Pros
- Easy to manage with its simplicity. All operational aspects like transaction tracing, monitoring etc become easy as well. 
- Service workflow becomes simple for the process won't proceed until the prediction completes.

## Cons
- The prediction latency can become a performance bottleneck.
- You might have to consider a workaround for not degrading your user experience because of prediction latency.
- If the client of your service is another service then this pattern leads to blocked threads on the client side.

## Needs consideration
- Work around for not making user experience getting worse for prediction latency.
- Needs timeout if the latency is too long.
  
## Sample
https://github.com/shibuiwilliam/ml-system-in-actions/tree/main/chapter4_serving_patterns/synchronous_pattern
