## continuous integration
- 여러 개발자가 같은 코드에 작업하면 merge hell 이 발생한다.
- 이것을 unit test 를 통해 지속적으로 통합하는 과정이다.

## continuous delivery
- 코드를 프로덕션에 배포하기 까지 다음과 같은 단계를 거친다.
  - code -> build (ci) -> qa -> stage -> production
 
- continuous delivery 란, 새로 작성한 코드를 프로덕션에 문제없이 배포함을 뜻한다.
1. 코드를 빌드 프로세스 (./gradlew builda) 에 올린다.
2. 문제가 없을 경우, auto-deploy 프로세스를 통해 QA 환경에 배포한다.
3. 테스트에 통과할 경우 auto-deploy 프로세스를 통해 stage 환경에 배포한다.
4. 이후 의사결정을 통해 production 환경에 배포한다.

# 클라우드 네이티브 책 정리
## CI
- build, test, artifact upload 를 자동으로 하는 방법
1. build: git 에 소스를 커밋하면 빌드한다.
2. test: 파이프라인을 통해 unit test, 기능 테스트, 인수 테스트, 정적 분석, 린트 등을 수행한다.
3. artifact upload: test단계에 통과하면, 버전 숫자나 commit ID 로 패키징하고 태그해서 아티팩트(docker image, function 파일 등)를 저장한다.

## CD
- 빌드되고 테스트된 아티팩트를 원하는 환경에 배포하는 것
1. 배포 단계: 스테이지 또는 프로덕션 환경에 아티팩트를 배포한다.
  - 스테이지 테스트 패턴: 트래픽 미러링, istio 의 VirtualService 를 통해 실제 트래픽을 미러링해서 스테이지 환경에 테스트 할 수 있다.
2. 출시 단계: 배포한 서비스를 충분히 테스트(UI 테스트 등)한 후, 실제 트래픽을 천천히 리다이렉팅 한다.
  - 서버리스 애플리케이션의 경우 Aws CodeDeploy, Azure Traffic Manager 등을 활용할 수 있다.
  - blue/green, rate limiting, A/B testing 등
  - 문제가 생기면 롤백을 해야 한다.
3. 출시 후 단계: 지속적으로 서비스를 모니터링하고 알림 등을 받는다.
