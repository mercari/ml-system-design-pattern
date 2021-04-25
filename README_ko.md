[English](./README.md) [Japanese](./README_ja.md) 
# 머신러닝 시스템 디자인 패턴 
실제 운영 환경에서의 머신러닝 시스템 학습과 서빙, 운영을 위한 시스템 디자인 패턴을 다루고 있습니다. 

## 목적
이 문서의 주된 목적은 실제 운영되는 머신러닝 시스템의 디자인 패턴을 설명하는 것입니다. 
<br>
내용에 따라 일부 활용 사례를 참조하지만, 이 문서는 머신러닝 모델 성능 향상을 시키기 위한 디자인 패턴을 설명하는 것은 아닙니다. 
<br>

## 필요 조건
이 문서에 있는 모든 머신러닝 시스템 패턴은 클라우드나 쿠버네티스 클러스터를 사용하여 배포하는 것을 전제로 설명합니다. 이 문서는 최대한 특정 프로그래밍 언어나 플렛폼에 의존하지 않도록 노력하나, Python은 머신러닝에서 가장 대중적인 언어임을 감안하여 대부분의 디자인 패턴은 Python으로 구현 가능하도록 되어 있습니다. 
<br>

## 문서로 읽기 
아래 링크로 더 편하게 문서를 읽어보세요. 
[GitHub Pages](https://mercari.github.io/ml-system-design-pattern/README_ko.html)

## Sample implementations
아래에서 일부 샘플 구현을 사용할 수 있습니다.
https://github.com/shibuiwilliam/ml-system-in-actions
## Patterns
### [Serving patterns](./Serving-patterns/README_ko.md)
서빙 패턴은 실제 운영 환경에서 머신러닝 모델을 이용할 수 있도록 만드는 일련의 시스템 디자인들입니다. 
 
- [Web single pattern](./Serving-patterns/Web-single-pattern/design_ko.md)


- [Synchronous pattern](./Serving-patterns/Synchronous-pattern/design_ko.md)


- [Asynchronous pattern](./Serving-patterns/Asynchronous-pattern/design_ko.md)


- [Batch pattern](./Serving-patterns/Batch-pattern/design_ko.md)


- [Prep-pred pattern](./Serving-patterns/Prep-pred-pattern/design_ko.md)


- [Microservice vertical pattern](./Serving-patterns/Microservice-vertical-pattern/design_ko.md)


- [Microservice horizontal pattern](./Serving-patterns/Microservice-horizontal-pattern/design_ko.md)


- [Prediction cache pattern](./Serving-patterns/Prediction-cache-pattern/design_ko.md)


- [Data cache pattern](./Serving-patterns/Data-cache-pattern/design_ko.md)


- [Prediction circuit break pattern](./Serving-patterns/Prediction-circuit-break-pattern/design_ko.md)


- [Multiple stage prediction pattern](./Serving-patterns/Multiple-stage-prediction-pattern/design_ko.md)
 

- Edge prediction pattern: To do

- [Antipatterns](./Serving-patterns/Anti-patterns/README_ko.md)

  - [Online bigsize pattern](./Serving-patterns/Anti-patterns/Online-bigsize-pattern/design_ko.md)

  - [All-in-one pattern](./Serving-patterns/Anti-patterns/All-in-one-pattern/design_ko.md)

### [QA patterns](./QA-patterns/README_ko.md)
예측 서버와 모델 평가하기 위한 패턴들입니다. 

- [Shadow AB-testing pattern](./QA-patterns/Shadow-ab-test-pattern/design_ko.md)


- [Online AB-testing pattern](./QA-patterns/Online-ab-test-pattern/design_ko.md)


- [Loading test pattern](./QA-patterns/Loading-test-pattern/design_ko.md)

- [Antipatterns](./QA-patterns/Anti-patterns/README_ko.md)

  - [Offline-only pattern](./QA-patterns/Anti-patterns/Offline-only-pattern/design_ko.md)

### [Training patterns](./Training-patterns/README_ko.md)
학습 파이프라인을 구성하기 위한 패턴들입니다. 


- [Batch training pattern](./Training-patterns/Batch-training-pattern/design_ko.md)


- [Pipeline training pattern](./Training-patterns/Pipeline-training-pattern/design_ko.md)


- [Parameter and architecture search pattern](./Training-patterns/Parameter-and-architecture-search-pattern/design_ko.md)


- [Antipatterns](./Training-patterns/Anti-patterns/README_ko.md)

  - [Only-me pattern](./Training-patterns/Anti-patterns/Only-me-pattern/design_ko.md)

  - [Training code in serving pattern](./Training-patterns/Anti-patterns/Training-code-in-serving-pattern/design_ko.md)

  - [Too many pipes pattern](./Training-patterns/Anti-patterns/Too-many-pipes-pattern/design_ko.md)

### [Operation patterns](./Operation-patterns/README_ko.md)
ML 학습 시스템의 설정과 로깅, 모니터링, 알람 시스템을 위한 관리 및 운영 패턴들입니다.


- [Model-in-image pattern](./Operation-patterns/Model-in-image-pattern/design_ko.md)


- [Model-load pattern](./Operation-patterns/Model-load-pattern/design_ko.md)


- [Data model versioning pattern](./Operation-patterns/Data-model-versioning-pattern/design_ko.md)


- [Prediction log pattern](./Operation-patterns/Prediction-log-pattern/design_ko.md)


- [Prediction monitoring pattern](./Operation-patterns/Prediction-monitoring-pattern/design_ko.md)


- [Parameter-based serving pattern](./Operation-patterns/Parameter-based-serving-pattern/design_ko.md)


- [Condition-based-serving pattern](./Operation-patterns/Condition-based-serving-pattern/design_ko.md)

- [Antipatterns](./Operation-patterns/Anti-patterns/README_ko.md)

  - [No logging pattern](./Operation-patterns/Anti-patterns/No-logging-pattern/design_ko.md)

  - [Nobody knows pattern](./Operation-patterns/Anti-patterns/Nobody-knows-pattern/design_ko.md)


### [Lifecycle patterns](./Lifecycle-patterns/README_ko.md)
실제 운영을 위한 ML 시스템 전체를 구성하기 위해 여러 패턴들을 조합한 패턴들입니다. 

- [Train-then-serve pattern](./Lifecycle-patterns/Train-then-serve-pattern/design_ko.md)


- [Training-to-serving pattern](./Lifecycle-patterns/Training-to-serving-pattern/design_ko.md)


- [Antipatterns](./Lifecycle-patterns/Anti-patterns/README_ko.md)

  -　Todo

---

## Committers

 * Yusuke Shibui ([@shibuiwilliam](https://github.com/shibuiwilliam))
 * Sung Yun Byeon ([@zzsza](https://github.com/zzsza))
 * Jiyeon Seo ([@jiyeonseo](https://github.com/jiyeonseo))
 * Daeyoon Jin ([@zetbouaka](https://github.com/zetbouaka))

## 기여하기

새로운 패턴을 추가하려면 [template_design.md](./template_design.md)를 템플릿으로 사용하여 Issue를 생성하고 Pull Request를 만들어 주세요.<br>
새로운 안티 패턴을 추가할 경우 [template_antipattern.md](./template_antipatter.md)를 템플릿으로 사용하여 Issue와 Pull Request를 만들어 주세요.<br>
더 개선될 점이나 변경, 질문이 있는 경우 Issue로 제안해주세요. <br>

Mercari에 기여하기 전 CLA를 주의 깊게 읽어주세요. 기여를 함으로써 CLA의 약관에 따라 이를 승낙하고 동의한 것으로 간주됩니다. 

https://www.mercari.com/cla/


## License

Copyright 2020 Mercari, Inc.

Licensed under the [MIT License](LICENSE).