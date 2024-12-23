## Abstraction
> ### 추상화란?
추상화(Abstraction)는 필요한 정보만 보여주고, 불필요한 세부사항은 숨기는 객체 지향 프로그래밍의 개념</br>
복잡한 시스템을 단순화하여 사용자가 중요한 기능에만 집중할 수 있게 도와줌

> ### 추상화의 예
- ATM 사용
    - 사용자는 "돈을 입금/출금"하는 방법만 알면 됨
    - 내부에서 카드 정보를 확인하거나 돈을 꺼내는 과정은 추상화되어 있음

- 스마트폰 사용
    - 버튼 하나로 카메라를 실행하고 사진을 찍지만, 내부적으로 렌드, 센서, 프로세서가 어떻게 동작ㅎ는지는 알 필요가 없음

- TV 리모컨
    - 사용자는 "채널 변경", "볼륨 조절"같은 기능만 조작하며, 내부에서 신호가 어떻게 전달되는지는 감춰져 있음

> ### 코드로 보기
1. 추상 클래스 사용
- 추상 클래스는 구체적인 구현 없이 설계만 정의
    ```java
    // 추상 클래스 정의
    abstract class Animal {
        // 추상 메서드 (구체적인 구현 없음)
        abstract void sound();

        // 일반 메서드 (공통 기능 제공)
        void eat() {
            System.out.println("먹는 중...");
        }
    }

    // 추상 클래스를 상속받은 클래스는 반드시 추상 메서드를 구현해야 함
    class Dog extends Animal {
        void sound() {
            System.out.println("멍멍");
        }
    }

    public class Main {
        public static void main(String[] args) {
            Animal dog = new Dog();
            dog.sound();  // 출력: 멍멍
            dog.eat();    // 출력: 먹는 중...
        }
    }
    ```

2. 인터페이스를 사용한 추상화
- 인터페이스는 클래스가 구현해야 할 동작을 정의
    ```java
    interface Vehicle {
        void start();
        void stop();
    }

    // 인터페이스 구현
    class Car implements Vehicle {
        public void start() {
            System.out.println("자동차 시동 켜짐");
        }

        public void stop() {
            System.out.println("자동차 시동 꺼짐");
        }
    }

    public class Main {
        public static void main(String[] args) {
            Vehicle myCar = new Car();
            myCar.start();  // 출력: 자동차 시동 켜짐
            myCar.stop();   // 출력: 자동차 시동 꺼짐
        }
    }
    ```

> ### 쉬운 요약
1. 추상화는 불필요한 세부사항을 감추고 중요한 기능만 보여주는 것
    - 사용자가 복잡한 내부 구현을 알 필요 없이, 필요한 기능에만 접근할 수 있도록 설계

2. 구현 방법
    - 추상 클래스: 공통 동작과 설계를 정의
    - 인터페이스: 구현해야 할 동작(행동)을 강제

3. 장점
    - 코드 단순화: 사용자와 개발자가 중요한 기능에만 집중할 수 있음
    - 유지보수 용이: 내부 구현이 변경되어도 외부 코드에 영향을 미치지 않음
    - 재사용성: 추상화된 설계를 기반으로 다양한 객체를 만들 수 있음

> ### 비유
1. 자동차 운전
    - 운전자는 페달과 핸들만 조작하며, 내부의 복잡한 엔진 작동 방식은 몰라도 됨

2. ATM 사용
    - 돈을 넣거나 뽑는 기능만 제공되며, 카드 정보 인증, 금액 확인 같은 내부 과정은 감춰져 있음

3. 스마트폰 카메라
    - 사진을 찍는 버튼만 누르면 되며, 렌즈와 센서가 작동하는 세부사항은 알 필요가 없음

[뒤로](java)