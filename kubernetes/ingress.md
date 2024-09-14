# Ingress: HTTP load balancing
- k8s service 객체는 OSI-4-layer, TCP/UDP 에서 작동한다.

### 가상 호스팅 패턴 - virtual hosting pattern
- virtual hosting 패턴을 통해 하나의 IP로 여러 도메인을 호스팅할 수 있다.
- k8s에서는 ingress를 통해 이 패턴을 구현한다.
- 이 패턴의 단점은 설정을 개발자가 적용해야 한다는 점인데, ingress 는 이를 단순화한다.

### ingress resource & ingress controller
- ingress 는 리소스 명세와 controller 로 나뉜다.
- ingress controller 로는 Nginx, AWS ALB, AGIC 등이 있으며, 내부적으로 LoadBalancer 또는 NodePort 등을 통해 외부 트래픽을 받는다.
  - LoadBalancer 타입은 주로 cloud resource 를 통해 사용하며, MetalLB 등 온프레미스 구현도 가능하다.

### ingress 주의점
- ingress controller 는 cluster 전체에 걸쳐, 글로벌하게 조정해야 한다.
- 하나의 namespace 의 ingress 객체가 다른 namespace 에서 문제를 일으킬 수 있다.
