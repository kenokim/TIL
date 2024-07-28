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




