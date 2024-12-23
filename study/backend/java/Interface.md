## Interface
> ### Interface란?
인터페이스(Interface)는 클래스가 특정 인터페이스를 구현하여 인터페이스에 정의된 메소드를 반드시 작성하도록 만드는 과정을 의미</br>
자바에서 클래스는 implements 키워드를 사용해 인터페이스를 구현하며, 인터페이스는 클래스가 수행해야 할 동작(메소드)을 강제

> ### 예
- 운송 계약
    - 배송 회사(클래스)는 "배송 가능"(인터페이스)이라는 계약을 체결하고, 반드시 물품을 배소아는 메소드를 제공해야 함

- 스마트폰 표준 충전기
    - 모든 스마트폰 제조사(클래스)는 "충전 가능"(인터페이스)이라는 표준을 준수해야 하며, 충전 기능을 구현해야 함

- 요리사 채용 계약
    - 요리사(클래스)는 "요리 가능"(인터페이스)이라는 계약에 따라 요리 기능을 반드시 제공해야 함

> ### 코드로 보기
1. 기본적인 인터페이스 구현
    ```java
    // 인터페이스 정의
    interface Animal {
        void sound();  // 추상 메서드
    }

    // 클래스가 인터페이스를 구현
    class Dog implements Animal {
        @Override
        public void sound() {
            System.out.println("멍멍!");
        }
    }

    class Cat implements Animal {
        @Override
        public void sound() {
            System.out.println("야옹!");
        }
    }

    public class Main {
        public static void main(String[] args) {
            Animal dog = new Dog();
            Animal cat = new Cat();

            dog.sound();  // 출력: 멍멍!
            cat.sound();  // 출력: 야옹!
        }
    }
    ```

2. 다중 인터페이스 구현
- 클래스는 여러 인터페이스를 동시에 고현할 수 있음
    ```java
    interface Flyable {
        void fly();
    }

    interface Swimmable {
        void swim();
    }

    class Duck implements Flyable, Swimmable {
        @Override
        public void fly() {
            System.out.println("오리가 날아갑니다!");
        }

        @Override
        public void swim() {
            System.out.println("오리가 헤엄칩니다!");
        }
    }

    public class Main {
        public static void main(String[] args) {
            Duck duck = new Duck();
            duck.fly();  // 출력: 오리가 날아갑니다!
            duck.swim(); // 출력: 오리가 헤엄칩니다!
        }
    }
    ```

> ### 쉬운 요약
1. 인터페이스는 클래스가 인터페이스의 규칙을 따라 메소드를 구현하는 과정
    - 인터페이스는 메소드의 "약속"만 정의하며, 실제 동작은 클래스에서 작성

2. 키워드
    - implements: 클래스가 인터페이스를 구현할 때 사용하는 키워드

3. 특징
    - 다중 인터페이스 구현 가능
    - 인터페이스를 구현한 클래스는 반드시 모든 메소드를 정의해야 함

> ### 비유
1. 운송 계약
    - "배송 가능" 계약(인터페이스)을 맺은 배송 회사(클래스)는 반드시 물품을 배송하는 기능을 제공해야 함

2. 스마트폰 표준 충전기
    - "충전 가능" 인터페이스를 준수하면, 모든 충전기가 특정 스마트폰에서 동작

3. 요리사 채용 계약
    - "요리 가능" 계약을 체결한 요리사는 요리 기능을 반드시 제공해야 함

[뒤로](../README.md#java-study-notes)