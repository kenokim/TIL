# ch1. intro
### 참고자료
- https://www.youtube.com/watch?v=_K-eupuDVEc

### 관계형 DB vs. NoSQL
  - 낮은 latency 요구사항
  - 관계형 데이터가 아님
  - JSON, yaml, xml 등을 serialize/deserialize 할 수 있기만 하면 됨
  - 아주 많은 양의 데이터 요구사항
- 이러한 경우가 아니라면 관계형 DB를 선택하는게 났다.

### 캐시 사용 시 유의할 점
- 어떤 데이터를 캐싱해야 하는가?
- 캐시 만료 정책은 어떠한가?
- 캐시 데이터와 원본의 일관성은 어떠한가? (transaction)
- 캐시 저장소가 SPOF가 되지는 않는가?
- 캐시 메모리 크기?
- 데이터 eviction 정책은 어떠한가?

### 데이터 센터
- Geo redundancy
- zone redundancy

### 정리
- 웹 계층은 stateless 로
- 모든 계층을 다중화
- 가능한 한 많은 데이터를 캐싱할 것
- 여러 데이터 센터를 지원할 것
- Static 컨텐츠는 CDN 으로
- 데이터 계층은 샤딩으로
- 각 계층을 독립적 서비스로
- 시스템을 모니터링하고 자동화 도구를 활용해라

## additional
### 기술 스택 정리
- 메시지 큐: kafka, Azure service bus, Azure event hubs
- 모니터링: prometheus, datadog, Azure monitor
- 로그: ELK 스택 (elasticsearch, logstash, kibana), elastic APM, loki 스택 (loki, promtail, grafana), Azure monitor (application insights, log analytics)
- 자동화 도구: gitops - argocd
