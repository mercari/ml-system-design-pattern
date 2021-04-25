# Web single pattern

## Usecase
- When you want to quickly release the predictor in the simplest architecture.

## Architecture
The web single pattern is an architecture that packs all the artifacts and code for the prediction model in a web server. Since the single server REST (or GRPC) interface, preprocess, and trained model are in one place, you can create and deploy them as a simple predictor.<br>
If you want to deploy multiple replicas, you need to deploy them behind a load balancer or proxy. In case you are using GRPC for the interface, you need to consider client side load balancing or layer-7 load balancer.<br>
To build your model into a web server, you can adopt either [model-in-image pattern](./../../Operation-patterns/Model-in-image-pattern/design_en.md) or [model-load pattern](./../../Operation-patterns/Model-load-pattern/design_en.md).

## Diagram
![diagram](diagram.png)

## Pros
- Able to use one programming language, such as Python, for the web server, preprocess and inference.
- Easy to manage because of it's simplicity.
- Easier troubleshooting.
- Minimal time-to-productionize post model training.
- It is usually suggested to start your production architecture with deploying your models in the web single pattern in a synchronous fashion.

## Cons
- Since all components are packed in a server or a docker image, applying a small patch will require updating the whole image
- Updates will also require a service deployment, which in bigger organizations requires one to follow a hefty SDLC

## Needs consideration
- Update and maintenance procedure for each component.
- Scale change management of the web server.

## Sample
https://github.com/shibuiwilliam/ml-system-in-actions/tree/main/chapter4_serving_patterns/web_single_pattern
