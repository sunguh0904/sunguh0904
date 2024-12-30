## AOP란?
> ### AOP 개요
AOP(Aspect-Oriented Programming)는 관점 지향 프로그래밍으로, 횡단 관심사를 모듈화하여 코드의 중복을 줄이고 유지보수를 용이하게 하는 프로그래밍 패러다임

> ### 주요 기능
1. **횡단 관심사 분리**: 로깅, 보안, 트랜잭션 관리 등 애플리케이션 전반에 걸쳐 반복적으로 사용되는 코드를 분리
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

2. **코드 중복 제거**: 공통 기능을 분리하여 코드 중복을 제거하고, 핵심 비즈니스 로직에 집중할 수 있게 함
    ```java
    @Aspect
    @Component
    public class SecurityAspect {
        @Before("execution(* com.example.service.*.*(..))")
        public void checkSecurity(JoinPoint joinPoint) {
            // 보안 체크 로직
        }
    }
    ```

3. **유지보수 용이**: 공통 기능을 한 곳에서 관리하여 유지보수가 용이함
    ```java
    @Aspect
    @Component
    public class TransactionAspect {
        @Around("execution(* com.example.service.*.*(..))")
        public Object manageTransaction(ProceedingJoinPoint joinPoint) throws Throwable {
            // 트랜잭션 관리 로직
            return joinPoint.proceed();
        }
    }
    ```

> ### 왜 사용해야 하는가?
1. **코드 중복 제거**: 공통 기능을 분리하여 코드 중복을 제거할 수 있음
2. **유지보수 용이**: 공통 기능을 한 곳에서 관리하여 유지보수가 용이함
3. **비즈니스 로직 집중**: 핵심 비즈니스 로직에 집중할 수 있음

> ### 쉬운 요약
1. AOP는 "관점 지향 프로그래밍"
    - 횡단 관심사를 모듈화하여 코드의 중복을 줄이고 유지보수를 용이하게 함

> ### 비유
1. 청소 도구 세트
    - AOP는 "청소 도구 세트"와 같음
    - 예: 다양한 청소 도구를 사용하여 집안 곳곳을 청소

2. 요리 준비 도구
    - AOP는 "요리 준비 도구"와 같음
    - 예: 다양한 요리 준비 도구를 사용하여 요리를 준비

[뒤로](SpringCore.md)
