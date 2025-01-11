## ch.07 신뢰성 있는 데이터 전달
- 신뢰성이란? 시스템이 서로 다른 상황에서 보장하는 것
  - RDBMS 의 ACID 보장
- trade-off: 신뢰성/일관성과 가용성/높은 처리량, 낮은 지연/비용 등은 trade-off 관계이다.
- kafka 는 모든 in-sync-replicas 의 partition 에 쓰여야 commit 된 것으로 간주하며, consumer 는 commit 된 메시지만 읽을 수 있다.

### 복제
- 각 topic 은 여러 partition 으로 이루어 지며, 각 partition 은 다수의 replica 를 가질 수 있다.
- 각 replica 는 leader 와 follower 로 나뉜다.
- leader replica 또는 조건을 맞추는 follower replica 는 in-sync replica 로 간주된다.

### broker
- replication.factor, unclean.leader.election.enable, min.insync.replicas
- 이 설정들은 신뢰성과 관련이 있다.

### producer
- acks=0: 메시지를 전송하자 마자 producer 는 성공 처리한다.
- acks=1: 메시지를 leader partition 이 쓴 후에 응답이 오면 producer 는 성공 처리한다.
- acks=all: min.insync.replicas 가 메시지를 받아가면 producer 는 성공 처리한다.

