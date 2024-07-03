# Azure service bus

## 주요 개념
- queue: FIFO 로 처리된다. 한 번 소비되면 큐에서 삭제된다.
- topic: pub/sub 패턴으로 one-to-many 통신을 가능하게 한다.
- subscription: 메시지를 토픽에 publish 하면 각 구독은 해당 메시지를 받아 처리한다.
- sessions: 메시지 순서 및 관리를 지원한다.
- TTL: 메시지의 유효 기간이 지나면 삭제된다.
- 중복 감지: 동일한 메시지가 중복해서 전달되는 것을 방지한다.
- namespace: 모든 메시징 구성 요소의 컨테이너로, 하나 이상의 큐와 토픽이 있을 수 있다.

