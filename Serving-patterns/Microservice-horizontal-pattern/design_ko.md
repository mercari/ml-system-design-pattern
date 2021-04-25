# Microservice horizontal pattern

## Usecase
- 워크플로우가 여러 예측을 병렬로 실행할 수 있는 경우.
- 마지막에 예측 결과를 통합하고 싶은 경우.
- 하나의 요청에 여러 예측을 하고 싶은 경우.


## Architecture
Microservice horizontal pattern은 여러 독립적인 모델을 병렬로 실행할 수 있습니다. 한번에 여러 모델에 예측을 요청해 여러 예측 결과나 통합된 예측 결과를 얻을 수 있습니다. <br>
활용 사례에 따라 동기 또는 비동기 방식 중 어떤 것을 사용할지 결정할 수 있습니다. 만약 동기 방식을 사용하면, 모든 모델의 예측 결과를 집계해 반환해야 합니다. 만약 비동기 방식을 사용하면, 특정 예측(`Asynchronized horizontal`)이 나오면 바로 다음 작업을 실행할 수 있습니다.<br>
클라이언트와 예측 서비스 사이에 프록시를 배치할 수도 있습니다. 프록시가 클라이언트에서 요청하는 데이터 검색 및 예측 순서를 제어하기를 기대할 수 있습니다. 프록시 또는 예측 서비스가 추가 데이터 검색을 수행하도록 할 수 있습니다(`Synchronized horizontal with data retrieval`). 데이터를 가져오는 프록시의 장점은 데이터웨어하우스 또는 스토리지에 대한 요청 수를 줄여 오버헤드를 줄이는 반면, 후자는 각 예측 모델에 따라 데이터 구조를 제어해 복잡한 워크플로우를 만들 수 있습니다.

## Diagram
### Synchronized horizontal
![diagram1](diagram1.png)

### Synchronized horizontal with data retrieval
![diagram2](diagram2.png)

### Asynchronized horizontal
![diagram3](diagram3.png)

## Pros
- 리소스 사용량을 독립적으로 조정하고 장애를 격리할 수 있습니다.
- 다른 모델에 의존성 없이 모델과 시스템을 개발할 수 있습니다.

## Cons
- 시스템이 복잡해질 수 있습니다.
- 동기 방식은 가장 느린 예측이 병목이 됩니다.
- 비동기 방식은 예측 지연 시간을 관리하도록 사후 처리를 해야 합니다.

## Needs consideration
- 동기식 또는 비동기식.
- 동기식에서 느린 모델을 관리하는 방법 : 타임아웃 또는 대기.
- 비동기식에서 시간 지연을 관리하는 방법.

## Sample
https://github.com/shibuiwilliam/ml-system-in-actions/tree/main/chapter4_serving_patterns/horizontal_microservice_pattern
