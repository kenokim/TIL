## FaaS 의 구성 요소
- 함수
- event stream
- trigger
- policy & metadata

### event
- key, value, timestamp, offset, partition id

### context
- 함수명, event stream ID, 함수 생명 주기 정보

### policy & metadata
- consumer group, consumer policy, retry & fallback, scaling policy

## Event stream listener pattern
- event stream 에 event 가 생성될 때 함수를 trigger 한다.
- consumer 의 역할을 자동화한다. event consuming & offset commit 등
- cloud FaaS 는 event broker 전용 trigger 를 제공한다.
- kafka 는 kafka connect 를 제공한다.

### event trigger
- 동기 trigger: 처리 순서를 유지한다.
- 비동기 trigger: 처리 순서가 중요하지 않을 때 사용한다.
- batch size, batch window: 한 번에 몇 개의 event를 처리하도록 할 지 설정하는 값이다.

## FaaS solution 확장
- 작업을 병렬화, 처리 순서가 중요하지 않은 데이터의 queue/event stream 처리에 쓰기 좋은 도구다.

## Serverless computing
- CSP가 infra 와 scale 을 관리한다.
- 개발자 관점에서는 event-driven programming model 에 속한다.
- CPU를 소모한 만큼만 비용을 지불한다.
- FaaS 는 serverless 의 일종으로, 다른 종류의 serverless 도 있다.

### Serverless 의 장단점
- 장점: 초기 비용이 낮다, 확장성이 좋다, 인프라 관리가 필요하지 않다, 개발이 빠르다.
- 단점: cold start, timeout, 상태 관리 어려움, 비용 예측 어려움, 벤더 종속성, 보안 문제, 디버깅 및 모니터링 어려움.

## Function
- 코드를 독립적인 형태로 관리해야 하며, 한 가지만 수행하고 한 종류의 event 에만 응답해야 한다.
- 함수들이 상호작용할 필요 없는 단순 병렬 실행 senario 에 적합하다.
- 제약 사항으로 cold start, timeout 이 있으나 dedicated / durable function 등 CSP 의 Function 은 전체 app 을 FaaS로 개발할 수 있을 만큼 성숙하다.
