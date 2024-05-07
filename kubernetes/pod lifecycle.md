## pod lifecycle
- pending, running, succeeded, failed
- pod 의 정보를 보면 status, phase, conditions 와 containers - containerstatus, state 를 확인할 수 있다.
- initContainers: container 가 기동되기 전에 초기화 setting 이 필요할 경우, initContainer 를 실행시켜서 volume, 보안 설정 등 초기화 script 를 실행한다.

### pending state
- initialized: true -> initContainer 가 완료된 후 true 로 바뀐다.
- podScheduled: true -> pod 가 자원에 따라 스케쥴링된 후 true 로 바뀐다.
- container image download -> container state 는 waiting 이 된다.
## container lifecycle
- waiting, running, terminated
