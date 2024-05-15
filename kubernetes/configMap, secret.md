## configMap
- workload 에 대한 설정정보를 정의한다.
- fileSystem 으로 사용할 경우, configMap 을 pod 에 mount 할 수 있다.
- key 는 파일 이름, value 는 파일 내용이 된다.

## secret
- 민감한 설정정보를 저장한다.
- secrets volume: secret 정보를 pod volume 에 mount 할 수 있다.
  
