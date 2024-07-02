# Messaging
## 메시징의 필요성
- 애플리케이션과 시스템 컴포넌트가 실시간으로 메시지를 전달하고 데이터를 교환한다.
  - 클라이언트/서버 구조 = 요청/응답 패러다임
  - 메시징 = 송신자/수신자 + 중개자(브로커)에 의존하는 비동기화 구조
- Queue & messaging pub/sub: Azure 에서는 event grid, event hubs, service bus 와 같은 서비스가 있다.

## messaging 기초
- 생산자/소비자: unicast, multicast, broadcast
- broker -> 클러스터링이 필요하다. 견고성, 영속성, 메시지 정보의 배포와 저장에 대해
- 메시지 전달: at least once, at most once, exactly once

## 메시징 패턴
- simple queue: 메시지를 읽고 지운다.
- pub/sub: 메시지를 발행할 경우 모든 listening subscriber 가 메시지를 받는다.
  - 소비자가 online 상태가 아닐 경우 메시지를 놓칠 수 있다.
 - concrete queue: 메시지를 읽고 지우지 않는다. '포인터' 개념이 있다.

## OSS 메시징 솔루션
- rabbitmq
- kafka: Azure event hubs 와 호환된다.
- NATS: '최대 한 번'을 multicast 로 제공한다. 기본은 pub/sub 이고 mqtt 도 지원한다. JetStream 영속성 구현체는 정확히 한 번 전달이 가능하다.

## Azure service bus
- RabbitMQ, ActiveMQ 와 유사한 기능을 제공하는 관리형 큐 서비스
- 단순 메시지 큐, pub/sub 패턴을 제공한다.
- queue: pulling 되는 FIFO 메시지 세트를 제공한다.
- topic: 다수의 소비자와의 메시징을 위한 pub/sub 패턴과 1:N 통신을 제공한다.
- subscription: 소비자는 구독을 통해 필터링 규칙에 따라 메시지를 받을 수 있다.

## Azure event hubs
- apache kafka 의 일부 기능을 제공하도록 설계되었다.

## Azure event grid
- Azure ecosystem 내의 다양한 대상으로 이벤트 소스를 라우팅할 수 있다.
- 예: service bus, event hubs, functions, logic apps, 기타 애플리케이션
- event 별로 과금되는 서버리스 제품이다.
- push 특성을 가지며 이는 push-pull 패턴과 다르다.
