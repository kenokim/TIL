# pod
## pod 란? 
- 동일한 실행 환경에서 동작하는 컨테이너 & 볼륨 집합
- 동일한 pod 위의 애플리케이션은 동일한 ip, port 공간, 동일한 호스트명을 공유한다.
  - 다른 pod 위에 있는 애플리케이션은 ip, 호스트명이 다르다.

## pod manifest
- spec.volumes: pod 의 모든 컨테이너가 접근할 수 있는 볼륨
- containers.volumeMounts: 특정 컨테이너에 마운트될 볼륨과 경로
 
## pod manifest 를 선언할 경우
- kubernetes API 서버는 manifest 를 수락하고 처리한다.
- 이후 etcd 에 저장한다.
- 스케쥴러는 API 서버를 통해 pod 를 노드에 배치한다.
