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

## resilience4j
- circuitbreaker 기능을 제공한다.
- application.properties 에서 설정 가능하다. 예를 들어, 3초 이상 걸리는 경우 캐싱된 값을 리턴한다.

```kotlin
import io.github.resilience4j.circuitbreaker.annotation.CircuitBreaker
import org.springframework.stereotype.Service
import java.time.Instant

@Service
class ExampleService(private val exampleClient: ExampleClient) {

    private val cachedPost = Post(0, "Cached Title", "Cached Content", Instant.now().toString())

    @CircuitBreaker(name = "exampleService", fallbackMethod = "fallbackGetPostById")
    fun getPostById(id: Long): Post {
        // API 호출 (3초 이상 지연될 경우 fallback 실행)
        return exampleClient.getPostById(id)
    }

    // Fallback 메서드
    fun fallbackGetPostById(id: Long, throwable: Throwable): Post {
        println("Fallback triggered due to: ${throwable.message}")
        return cachedPost.copy(id = id, timestamp = Instant.now().toString())
    }
}

```
