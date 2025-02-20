## timezone 이란?
- 애플리케이션은 사용자의 로컬 시간대를 고려해야 한다.
- 이 때, timezone 은 UTC 와의 offset 으로, 사용자의 로컬 시간을 계산할 때 활용된다.

## 서버의 timezone
- 서버의 timezone 은 애플리케이션이 사용하는 시간대이다.
- 예를 들어, Java 에서 LocalDateTime.now(); 를 호출할 경우 기본적으로 서버의 timezone 을 따른다.

## Docker 컨테이너의 timezone
- 기본적으로 컨테이너의 OS 를 따른다.
- 예를 들어, Ubuntu 는 기본값이 UTC 이다.
- 컨테이너의 timezone 은 서버의 timezone 과 다를 수 있다.

## Java 의 timezone
- 기본적으로 OS 의 timezone 을 따른다.
- JVM 실행 시 -Duser.timezone 플래그로 시작 시점에 전역으로 설정할 수 있다.
- TimeZone.setDefault() 를 통해 런타임에 전역으로 설정할 수 있다.
- 특정 메소드에서 ZoneId 를 통해 timezone 을 적용한 후 시간값을 반환할 수 있다.

### Java 의 TimeZone 클래스
<img width="428" alt="스크린샷 2025-02-20 오후 11 49 10" src="https://github.com/user-attachments/assets/73cd7bba-9a14-4032-8a77-20fec1a56808" />
<img width="645" alt="스크린샷 2025-02-20 오후 11 52 48" src="https://github.com/user-attachments/assets/b66011bd-52c8-49d8-bd88-a5bee95e5eba" />

- TimeZone.getDefault() 를 호출할 경우, defaultTimeZone 이 있을 경우 (setDefault 를 통해 세팅된 경우 등) 그 값을 리턴하고, 없을 경우 System 의 user.timezone (JVM 실행 플래그) 에서 읽어온다.
