# Offline only pattern

## Case
- 머신러닝 모델이 오프라인 테스트 데이터로만 평가되는 경우.

## Situation
- 머신러닝 모델의 비즈니스 가치는 모델이 프러덕션 서비스에 구현될 때 입증될 수 있으며, 비즈니스 KPI를 개선하거나 효율성에 기여할 수 있습니다. 모델이 유용한지 결정하는 것은 실제로 비즈니스를 기준으로만 평가할 수 있으며 테스트 데이터에선 평가할 수 없습니다. 테스트 데이터 세트는 모델 출시 여부를 결정하는 기준 중 하나일 수 있지만 테스트 데이터는 비즈니스 KPI가 아닙니다. 테스트 데이터세트에서 모델이 99.99%의 정확도를 기록하더라도 실제 데이터에서 효과를 발휘하지 않는다면(또는 부정적인 영향을 미친다면) 이 모델은 유효하다고 할 수 없습니다. 예측 모델로 출시한 모델은 운영 환경에서 효과를 검증해야 합니다. 만약 모델이 운영 환경에서 성능이 저조하거나 더 나빠질 경우 모델에 대한 요청을 중지하고 모델을 사용하지 않았을 때로 되돌리는 것을 권장합니다. [Parameter-based serving pattern](../../../Operation-patterns/Parameter-based-serving-pattern/design_ko.md)를 사용하면 부정적인 영향을 피하며 쉽게 되돌릴 수 있습니다. 

## Diagram
![diagram](diagram.png)


## Pros
- 없습니다.

## Cons
- 비즈니스에 미치는 영향을 기준으로 모델을 평가하지 않습니다.

## Work around
- 프러덕션 모델로 개선할 KPI를 정의하고, 출시 전 상태와 출시 상태(A/B 테스트의 경우 A 그룹과 B 그룹)의 비교를 분석합니다. 모델 영향을 평가하기 위해 로그를 정의하고, 모델을 평가하기 위해 충분한 로그가 수집되면 모델을 평가해 모델을 계속 사용할지 여부를 결정합니다. 계속 사용한다면, 모델을 개선하는 방법을 찾아봅시다.

## Related design pattern
- [Shadow AB-testing pattern](./../../Shadow-ab-test-pattern/design_ko.md)
- [Online AB-testing pattern](./../../Online-ab-test-pattern/design_ko.md)
