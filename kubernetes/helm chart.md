# helm - kubernetes package manager
## 도입 배경
- 많은 오브젝트를 관리할 때, 오브젝트 별로 yml 파일을 작성해야 하므로 유지보수가 어려워진다.
- 하나의 template 을 통해 yml 파일을 동적으로 생성하게 해 주는 tool 이 필요하다.

## helm v3
- Helm client 가 cluster 의 api server 에 REST 요청을 하는 방식으로 구현되었다.
