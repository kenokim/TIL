## ch07. Service discovery & service mesh
### service discovery
- service discovery 는 개별 service 들이 서로를 자동으로 찾고 통신할 수 있도록 도와주는 메커니즘이다.
  - kubernetes 에서 service 기능이 이에 해당한다.
  - CoreDNS: k8s 의 기본 service discovery mechanism 으로 DNS 서버 역할을 한다.
### 구성 요소
- service registry: 모든 서비스 인스턴스가 자신의 위치, ip/port 를 등록하고 client가 조회할 수 있도록 하는 중앙 저장소
  - eureka, etcd, zookeeper

### service mesh
- sidecar pattern 으로 관측성, 안정성, 보안을 추가로 제공하는 기능
- istio

