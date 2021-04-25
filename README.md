[Japanese](./README_ja.md) [Korean](./README_ko.md)
# Machine learning system design pattern
This repository contains system design patterns for training, serving and operation of machine learning systems in production.

## Objectives
The main objective of this document is to explain system patterns for designing machine learning system in production. <br>
This document is not the design patterns for developing machine learning model to achieve certain performance in accuracy, though some columns may refer to those use-cases.
<br>

## Prerequisites
All of the ML system patterns are designed to be deployed on a public cloud or a Kubernetes cluster. The document tries not to be dependent on a certain programming language or platform as possible, though since Python is the most major language for the machine learning technology, most of the patterns can be developed with Python.
<br>

## For reading
Please refer below for reading:<br>
[GitHub Pages](https://mercari.github.io/ml-system-design-pattern/)

## Sample implementations
Some sample implementations are available below.
https://github.com/shibuiwilliam/ml-system-in-actions

## Patterns
### [Serving patterns](./Serving-patterns/README.md)
The serving patterns are a series of system designs for using machine learning models in production workflow.
- [Web single pattern](./Serving-patterns/Web-single-pattern/design_en.md)


- [Synchronous pattern](./Serving-patterns/Synchronous-pattern/design_en.md)


- [Asynchronous pattern](./Serving-patterns/Asynchronous-pattern/design_en.md)


- [Batch pattern](./Serving-patterns/Batch-pattern/design_en.md)


- [Prep-pred pattern](./Serving-patterns/Prep-pred-pattern/design_en.md)


- [Microservice vertical pattern](./Serving-patterns/Microservice-vertical-pattern/design_en.md)


- [Microservice horizontal pattern](./Serving-patterns/Microservice-horizontal-pattern/design_en.md)


- [Prediction cache pattern](./Serving-patterns/Prediction-cache-pattern/design_en.md)


- [Data cache pattern](./Serving-patterns/Data-cache-pattern/design_en.md)


- [Prediction circuit break pattern](./Serving-patterns/Prediction-circuit-break-pattern/design_en.md)


- [Multiple stage prediction pattern](./Serving-patterns/Multiple-stage-prediction-pattern/design_en.md)
 
- [Serving template pattern](./Serving-patterns/Serving-template-pattern/design_en.md)

- Edge prediction pattern: To do

- [Antipatterns](./Serving-patterns/Anti-patterns/README.md)

  - [Online bigsize pattern](./Serving-patterns/Anti-patterns/Online-bigsize-pattern/design_en.md)

  - [All-in-one pattern](./Serving-patterns/Anti-patterns/All-in-one-pattern/design_en.md)

### [QA patterns](./QA-patterns/README.md)
Pattens to evaluate model as well as prediction server.
- [Shadow AB-testing pattern](./QA-patterns/Shadow-ab-test-pattern/design_en.md)


- [Online AB-testing pattern](./QA-patterns/Online-ab-test-pattern/design_en.md)


- [Loading test pattern](./QA-patterns/Loading-test-pattern/design_en.md)

- [Antipatterns](./QA-patterns/Anti-patterns/README.md)

  - [Offline-only pattern](./QA-patterns/Anti-patterns/Offline-only-pattern/design_en.md)

### [Training patterns](./Training-patterns/README.md)
Patterns to construct training pipeline.
- [Batch training pattern](./Training-patterns/Batch-training-pattern/design_en.md)


- [Pipeline training pattern](./Training-patterns/Pipeline-training-pattern/design_en.md)


- [Parameter and architecture search pattern](./Training-patterns/Parameter-and-architecture-search-pattern/design_en.md)


- [Antipatterns](./Training-patterns/Anti-patterns/README.md)

  - [Only-me pattern](./Training-patterns/Anti-patterns/Only-me-pattern/design_en.md)

  - [Training code in serving pattern](./Training-patterns/Anti-patterns/Training-code-in-serving-pattern/design_en.md)

  - [Too many pipes pattern](./Training-patterns/Anti-patterns/Too-many-pipes-pattern/design_en.md)

### [Operation patterns](./Operation-patterns/README.md)
The operation patterns contain configuration, logging, monitoring and alerting system designs for machine learning system.
- [Model-in-image pattern](./Operation-patterns/Model-in-image-pattern/design_en.md)


- [Model-load pattern](./Operation-patterns/Model-load-pattern/design_en.md)


- [Data model versioning pattern](./Operation-patterns/Data-model-versioning-pattern/design_en.md)


- [Prediction log pattern](./Operation-patterns/Prediction-log-pattern/design_en.md)


- [Prediction monitoring pattern](./Operation-patterns/Prediction-monitoring-pattern/design_en.md)


- [Parameter-based serving pattern](./Operation-patterns/Parameter-based-serving-pattern/design_en.md)


- [Condition-based-serving pattern](./Operation-patterns/Condition-based-serving-pattern/design_en.md)

- [Antipatterns](./Operation-patterns/Anti-patterns/README.md)

  - [No logging pattern](./Operation-patterns/Anti-patterns/No-logging-pattern/design_en.md)

  - [Nobody knows pattern](./Operation-patterns/Anti-patterns/Nobody-knows-pattern/design_en.md)


### [Lifecycle patterns](./Lifecycle-patterns/README.md)
The lifecycle patterns contain composition of several patterns to realize actual ML system with operation.
- [Train-then-serve pattern](./Lifecycle-patterns/Train-then-serve-pattern/design_en.md)


- [Training-to-serving pattern](./Lifecycle-patterns/Training-to-serving-pattern/design_en.md)


- [Antipatterns](./Lifecycle-patterns/Anti-patterns/README.md)

  -　Todo

---

## Committers

 * Yusuke Shibui ([@shibuiwilliam](https://github.com/shibuiwilliam))
 * Sung Yun Byeon ([@zzsza](https://github.com/zzsza))
 * Jiyeon Seo ([@jiyeonseo](https://github.com/jiyeonseo))
 * Daeyoon Jin ([@zetbouaka](https://github.com/zetbouaka))

## Contribution

For adding a new pattern, please use [template_design.md](./template_design.md) as a template, and raise an issue and later PR.<br>
For adding a new antipattern, please use [template_antipattern.md](./template_antipattern.md) as a template, and raise an issue and later PR.<br>
To request for improvement, change or question, please propose an issue.<br>

Please read the CLA carefully before submitting your contribution to Mercari.
Under any circumstances, by submitting your contribution, you are deemed to accept and agree to be bound by the terms and conditions of the CLA.

https://www.mercari.com/cla/


## License

Copyright 2020 Mercari, Inc.

Licensed under the [MIT License](LICENSE).