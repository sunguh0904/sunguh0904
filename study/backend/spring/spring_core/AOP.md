## AOP란?
> ### AOP 개요
AOP(Aspect-Oriented Programming)는 관점 지향 프로그래밍으로, 횡단 관심사를 모듈화하여 코드의 중복을 줄이고 유지보수를 용이하게 하는 프로그래밍 패러다임</br>
기존의 코드를 변경하지 않고 새로운 기능을 추가하는 방식으로 사용</br>
스프링에서는 AOP를 이용해 로깅, 트랜잭션, 보안 등의 기능을 제공

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

> ### Aspects
별도의 spring-aspects 모듈은 AspectJ와의 통합을 제공

> ### Instrumentation
Instrumentation은 자바 프로그램의 동작을 관찰하고 조작하는 기술</br>
스프링에서는 Instrumentation을 이용해 클래스 로딩, 메소드 실행 등의 작업을 추적하고 변경할 수 있음

> ### Messaging
Apache Kafka 및 RabbitMQ와 같은 메시지 브로커의 통합을 통해 메시징 아키텍처를 지원</br>
메시지 채널, 메시지 처리기 및 메시징 기반 응용 프로그램을 생성할 수 있는 메시지 끝점에 대한 추상화가 포함됨</br>
메시지 채널에서 메시지를 수신하고 처리할 수 있는 메시지 구동 POJO(Plain Old Java Objects)를 생성할 수 있음

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
