## kafka vs. event hubs
| Kafka Concept   | Event Hubs Concept |
|-----------------|--------------------|
| Cluster         | Namespace          |
| Topic           | An event hub       |
| Partition       | Partition          |
| Consumer Group  | Consumer Group     |
| Offset          | Offset             |

### clients
- AMQP, HTTPS, kafka client 를 사용할 수 있다.

### event hubs capture
- event hub 의 스트리밍 데이터를 blob storage 또는 data lake storage 로 파이프라이닝 할 수 있다.

### partitions vs throughput units
- 둘 다 확장성에 관련된 값이다.
- partitions 는 병렬 처리에 대해, throughput units 은 이벤트 스트림의 처리량에 대한 값이다.
