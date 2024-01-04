# Test Containers
- 테스트를 실행할 때 docker testcontainers 를 통해 production 환경에서 사용하는 db 와 같은 구성을 쓸 수 있다.
- Container 를 테스트 전에 띄우고, 테스트 후에 삭제하는 등 관리 작업을 자동화 해 준다.
- 라이브러리에서 공식적으로 지원하는 모듈이 있고 (postgresql, redis 등) 이에 대한 가이드가 나와 있다.
- Container 의 주소는 런타임에 가져와서 jdbc, jedis 등에 설정해줘야 한다.
