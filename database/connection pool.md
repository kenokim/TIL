## conenction pool
- 커넥션 풀 이란?
  - 웹 애플리케이션 서버가 데이터베이스에 커넥션을 미리 연결해 놓고 pool 로 구성하여 사용하는 방법이다.
  - Spring 에서는 HikariCP 라는 오픈소스를 사용한다.

- 커넥션이란?
  - TCP/IP 커넥션을 의미한다.
  - 커넥션 풀은 TCP 3-way handshake 를 미리 해 놓아 응답 지연을 줄이고자 한다.
  - 또한, 커넥션 수를 관리함으로써 리소스 사용을 제한할 수 있다.

## HikariCP 옵션

| **옵션** | **설명** | **기본값** |
|---------|--------|-----------|
| `maximumPoolSize` | 최대 Connection 개수 | **10** |
| `minimumIdle` | 유지할 최소 Connection 개수 | **same as `maximumPoolSize`** |
| `idleTimeout` | Idle 상태의 Connection을 제거하는 시간 (밀리초) | **600000 (10분)** |
| `maxLifetime` | Connection이 사용 가능한 최대 시간 (밀리초) | **1800000 (30분)** |
| `connectionTimeout` | Connection을 얻기 위한 최대 대기 시간 (밀리초) | **30000 (30초)** |
| `leakDetectionThreshold` | Connection이 반환되지 않으면 로그 출력 (밀리초) | **0 (비활성화)** |
| `autoCommit` | Connection 사용 후 자동 커밋 여부 | **true** |
| `validationTimeout` | Connection의 유효성을 검사하는 최대 시간 (밀리초) | **5000 (5초)** |
| `keepaliveTime` | Connection이 비활성 상태일 때 ping을 보내는 시간 (밀리초) | **0 (비활성화)** |
| `poolName` | Connection Pool의 이름 | **HikariPool-1** |
| `allowPoolSuspension` | Pool의 동작을 일시 중지할 수 있는지 여부 | **false** |
| `isReadOnly` | Connection을 Read-Only로 설정할지 여부 | **false** |
| `registerMbeans` | JMX로 HikariCP 상태를 모니터링할 수 있는지 여부 | **false** |

 
- TCP 연결에는 어떤 물리적인 리소스가 사용되는가?
- TCP 연결은 여러 가지 리소스를 사용합니다. 주요한 것들은 다음과 같습니다:
  - 메모리: TCP 연결은 각 연결마다 상태 정보를 유지해야 하므로 메모리를 사용합니다. 이는 연결의 현재 상태, 패킷의 전송 및 수신 상태, 및 기타 연결 관련 정보를 저장하는 데 사용됩니다.
  - 대역폭: TCP 연결은 데이터를 전송하기 위해 대역폭을 사용합니다. 전송되는 데이터의 양과 전송 속도는 연결의 특성에 따라 달라집니다.
  - CPU 자원: TCP 연결은 패킷을 처리하고 데이터를 인코딩 및 디코딩하는 데 CPU 자원을 사용합니다. 특히, 데이터의 암호화 및 해독이 필요한 경우 이 작업은 CPU 자원을 많이 사용할 수 있습니다.
  - 네트워크 리소스: TCP 연결은 네트워크 인터페이스와 관련된 리소스를 사용합니다. 이는 데이터를 전송하고 수신하기 위한 네트워크 인터페이스의 대역폭 및 기타 기능을 포함합니다.
- 물론 이건 기본적인 요소일 거고, 프로토콜 자체에 성능 최적화를 위해 추가로 사용하는 요소도 있을 것이다.

- 커넥션 풀 자체는 웹 애플리케이션 서버의 리소스이다. 하드웨어 리소스가 충분하다면 이를 늘릴 수 있다.
- 커넥션 풀을 늘렸을 때 발생할 수 있는 문제점
  - 리소스 고갈: 커넥션 풀은 메모리 및 기타 시스템 리소스를 사용합니다. 무한대로 커넥션 풀 크기를 늘리면 시스템 리소스가 고갈될 수 있습니다. 이는 다른 어플리케이션의 성능에 영향을 미칠 수 있습니다.
  - 성능 하락: 커넥션 풀의 크기가 너무 크면 관리 오버헤드가 증가할 수 있습니다. 커넥션을 생성하고 해제하는 작업은 비용이 많이 들 수 있으며, 이로 인해 어플리케이션의 전체 성능이 감소할 수 있습니다.
  - 데드락: 커넥션 풀을 너무 크게 설정하면 동시에 많은 커넥션을 처리해야 합니다. 이는 데드락(Deadlock)이 발생할 가능성을 높일 수 있습니다. 특히, 데이터베이스 자원에 대한 경쟁이 발생할 때 발생할 수 있습니다.
  - 데이터베이스 부하: 커넥션 풀이 너무 크면 동시에 많은 연결이 데이터베이스에 요청될 수 있습니다. 이는 데이터베이스의 부하를 증가시킬 수 있으며, 성능 문제를 초래할 수 있습니다.

- 의문점 1. jdbc 커넥션 풀은 항상 tcp/ip 만 사용하는가?
  - 아닌 경우도 있다고 한다. unix 소켓이나 ipc 를 사용하는 경우도 있다.
 
- 의문점 2. 데이터베이스는 왜 tcp 를 요청 프로토콜로 사용할까? 엘라스틱서치처럼 http 와같은 상위레벨로 옮기는 db는 없을까?
