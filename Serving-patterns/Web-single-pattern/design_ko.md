# Web single pattern

## Usecase
- 가장 간단한 아키텍처에서 예측 서버를 빠르게 출시하고 싶은 경우.

## Architecture
Web single pattern은 예측 모델을 위한 모든 아티팩트를 웹 서버에 함께 저장하는 구조입니다. 단일 서버 REST(또는 GRPC) 인터페이스, 전처리, 훈련된 모델을 한 곳에서 사용하기 때문에 예측 서버를 간단히 생성하고 배포할 수 있습니다.<br>
만약 여러 복제본을 배포하려면, 로드 밸런서나 프록시를 사용해 배포할 수 있습니다. 인터페이스에 GRPC를 사용하는 경우, 클라이언트측 로드 밸런싱 또는 L7 로드 밸런서를 고려해야 합니다. <br>
웹 서버에 모델을 빌드하려면, [Model-in-image pattern](./../../Operation-patterns/Model-in-image-pattern/design_ko.md) 또는 [Model-load pattern](./../../Operation-patterns/Model-load-pattern/design_ko.md) 중 하나를 적용할 수 있습니다.


## Diagram
![diagram](diagram.png)

## Pros
- 웹 서버, 전처리, 예측할 때 파이썬 같은 하나의 프로그래밍 언어를 사용할 수 있습니다.
- 아키텍처의 단순함으로 관리가 쉽습니다.
- 트러블슈팅은 복잡하지 않습니다.
- 동기식 시스템에서 모델을 배포하기 위해 웹 단일 패턴으로 시작할 것을 제안합니다.

## Cons
- 모든 구성요소가 서버 또는 도커 이미지에 저장되므로 작은 패치를 적용하려면 전체 업데이트가 필요합니다.

## Needs consideration
- 각 구성 요소의 업데이트 및 유지보수 절차
- 웹 서버의 규모 변경 관리

## Sample
https://github.com/shibuiwilliam/ml-system-in-actions/tree/main/chapter4_serving_patterns/web_single_pattern
