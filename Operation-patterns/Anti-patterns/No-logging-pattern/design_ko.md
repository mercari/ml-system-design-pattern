# No logging pattern

## Case
- 로그나 프로파일을 관리하지 않는 경우. 

## Situation
머신러닝뿐만 아니라 모든 시스템 운영과 개선을 위해서 로그를 남기는 것은 정말 중요합니다. 로그가 없으면, 시스템을 마치 블랙박스처럼 만들어 에러를 찾고 트러블 슈팅을 하거나 환경 개선을 하는 것이 불가능해집니다. 특히, 머신러닝 시스템의 경우, 연관 이벤트 로그와 예측 결과를 통해 시스템과 모델을 개선할 수도 있고 비즈니스 계획에 도움을 줄 수 있습니다.<br>
머신러닝 작업에서 흥미롭고 도전적인 부분은 머신러닝이 실제 비즈니스 분야나 사용자 경험과 밀접하게 관련되어 있다는 점입니다. 정교한 방식으로 어떠한 행동이나 자동화를 예측하는 것은 기존의 if-else 문 만으로는 실현하기 정말 어려운 것이었지만, 머신러닝을 통해서는 해결해 낼 수도 있습니다. 비즈니스나 사용자 행동 심지어 물리적인 환경(IoT나 EdgeAI)에 영향을 준다는 것은 계속 바뀌는 실제 환경에 적합해야 하고, 이는 모델과 시스템 입장에서 추적할 수 있어야 한다(로그를 수집해야 한다)는 점을 유의해야 합니다.

## Diagram
![diagram](diagram.png)


## Pros
- 로그 보관 비용이 들지 않습니다. 

## Cons
- 시스템을 운영하거나 개선할 수 없습니다. 

## Work around
- 최소한의 Fatal, Error, Warning, Info 레벨의 로그는 남겨야 합니다.
- 추적 가능한 이벤트 로그를 정의하고 구현해야 합니다. 

## Related design pattern
- [Prediction log pattern](./../../Prediction-log-pattern/design_en.md)
- [Prediction monitoring pattern](./../../Prediction-monitoring-pattern/design_en.md)
