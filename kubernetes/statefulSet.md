# StatefulSet object
- 일반적으로 상태(state) 를 갖는 애플리케이션(데이터베이스)을 효과적으로 관리하고 안정적으로 배포하기 위해 사용한다.
- 각 pod 는 고유한 네트워크 식별자를 가지며, 파드의 순서와 식별자를 유지한다.
- 이를 통해 파드가 생성/scale-out 또는 삭제/scale-in 할 때 순서와 식별을 유자할 수 있다.
- 또한, 각 파드에 고유한 DNS name 을 제공하여 다른 애플리케이션과 통신할 때 파드를 식별할 수 있다.

## headless service
- statefulSet 의 리플리카 파드는 식별성을 가지므로, 일반적인 service 를 통해 로드밸런싱 하기보다는 headless service 를 사용한다.
- headless service 는 clusterIp (->단일 접근점)를 갖지 않는 서비스로, pod 의 dns 에 매핑할 수 있다.
- 예를 들어, redis 를 master 와 replica 로 배포할 경우, headless service 를 통해 쓰기 트래픽만 master 로 라우팅할 수 있다.

## persistentVolumeClaim
- pvc 를 통해 pod 의 생성과 스토리지의 생성에 대한 관리를 분리할 수 있다.
- statefulSet 를 사용할 때 pvc 를 통해 pv 를 요청하는데, 이를 통해 pod 를 생성할 때 자동으로 pv 를 할당할 수 있다.
