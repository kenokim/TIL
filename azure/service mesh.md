# service mesh
- networking concerns 에 대한 문제를 해결하기 위한 솔루션
  - istio, linkerd 등
- 요청 재시도, 타임아웃, 서킷 브레이커 등을 정의할 방법이 필요하다.
- 이에 대해, 라이브러리는 코드 언어 종속성이 생기므로, 다른 접근이 필요하다.
- 각 서비스 인스턴스에서 실행하는 프록시를 통해 이러한 기능을 제공한다.
- 프록시는 sidecar pattern 으로 구현된다.

## 서비스 메시 구조
- data plane: 서비스 메시 내 모든 프록시
- control plane: 데이터 플레인에 있는 프록시를 관리하는 요소

## dapr vs service mesh?
- dapr 는 마이크로서비스 개발을 쉽게 하기 위한 개발자 솔루션
- service mesh 는 네트워크 문제를 해결하기 위한 인프라 솔루션
