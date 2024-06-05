# OpenFeign
## 기능 목록
1. Declarative REST client
2. load balancing
3. circuit braker
4. retry mechanism
5. fallback
6. custom configuration
7. request interceptors
8. error handling

## 코드 예제
```java
@FeignClient(name = "user-service", fallback = UserServiceFallback.class)
public interface UserServiceClient {
    @GetMapping("/users/{id}")
    User getUserById(@PathVariable("id") Long id);
}

@Component
public class UserServiceFallback implements UserServiceClient {
    @Override
    public User getUserById(Long id) {
        return new User(); // 기본 응답 또는 에러 처리 로직
    }
}

@Component
public class FeignClientInterceptor implements RequestInterceptor {
    @Override
    public void apply(RequestTemplate template) {
        template.header("Authorization", "Bearer " + getToken());
    }
}

public class CustomErrorDecoder implements ErrorDecoder {
    @Override
    public Exception decode(String methodKey, Response response) {
        switch (response.status()) {
            case 400:
                return new BadRequestException();
            case 404:
                return new NotFoundException();
            default:
                return new Exception("Generic error");
        }
    }
}
```
