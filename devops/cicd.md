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
