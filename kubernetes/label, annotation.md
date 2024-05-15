## label
- kubernetes 객체에 연결할 수 있는 key/value pair로, 객체에 식별 정보를 첨부한다.
- label selector 를 통해 label 의 집합 기반으로 객체를 필터링할 수 있다.
  - kubectl get pods --selector="app=hello"
  - 객체가 다른 객체를 선택할 때 사용한다.
 
## annotation
- 시스템, 도구 및 라이브러리에서 활용할 수 있는 비식별 정보를 첨부한다.
- 필드, 이미지 정보, 디버깅 정보, 사용자 지시 사항 등
