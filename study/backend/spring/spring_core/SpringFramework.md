## Spring Framework란?
> ### Spring Framework 개요
Spring Framework는 자바 플랫폼을 위한 오픈 소스 애플리케이션 프레임워크로, 엔터프라이즈 애플리케이션 개발을 단순화하고 생산성을 높이기 위해 설계됨

> ### 주요 기능
1. **의존성 주입 (Dependency Injection)**: 객체 간의 의존성을 설정 파일이나 어노테이션을 통해 주입
    ```java
    @Component
    public class MyService {
        private final MyRepository myRepository;

        @Autowired
        public MyService(MyRepository myRepository) {
            this.myRepository = myRepository;
        }
    }
    ```

2. **AOP (Aspect-Oriented Programming)**: 횡단 관심사를 모듈화하여 코드의 중복을 줄이고 유지보수를 용이하게 함
    ```java
    @Aspect
    @Component
    public class LoggingAspect {
        @Before("execution(* com.example.service.*.*(..))")
        public void logBefore(JoinPoint joinPoint) {
            System.out.println("Method: " + joinPoint.getSignature().getName());
        }
    }
    ```

3. **트랜잭션 관리**: 선언적 트랜잭션 관리를 통해 데이터베이스 트랜잭션을 쉽게 처리
    ```java
    @Service
    public class MyService {
        @Transactional
        public void performTransaction() {
            // 트랜잭션 처리 로직
        }
    }
    ```

4. **MVC (Model-View-Controller)**: 웹 애플리케이션 개발을 위한 MVC 아키텍처 제공
    ```java
    @Controller
    public class MyController {
        @GetMapping("/hello")
        public String hello(Model model) {
            model.addAttribute("message", "Hello, Spring!");
            return "hello";
        }
    }
    ```

> ### 왜 사용해야 하는가?
1. **생산성 향상**: 의존성 주입과 AOP를 통해 코드의 중복을 줄이고 생산성을 높일 수 있음
2. **유연성**: 다양한 모듈과 통합하여 유연하게 애플리케이션을 개발할 수 있음
3. **유지보수 용이**: 트랜잭션 관리와 MVC 아키텍처를 통해 유지보수가 용이함

> ### 쉬운 요약
1. Spring Framework는 "자바 플랫폼을 위한 오픈 소스 애플리케이션 프레임워크"
    - 의존성 주입, AOP, 트랜잭션 관리, MVC 아키텍처를 제공

> ### 비유
1. 만능 도구 상자
    - Spring Framework는 "만능 도구 상자"와 같음
    - 예: 다양한 도구를 사용하여 애플리케이션을 개발하고 유지보수

2. 요리 레시피
    - Spring Framework는 "요리 레시피"와 같음
    - 예: 레시피를 따라 다양한 요리를 만들고 관리

[뒤로](SpringCore.md)
