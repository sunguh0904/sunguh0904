## Super
> ### Super란?
Super는 부모 클래스의 멤버(필드, 메소드, 생성자)에 접근하거나 호출할 때 사용되는 키워드</br>
자식 클래스가 부모 클래스의 기능을 확장하거나 재정의하면서, 기존 부모 클래스의 기능을 활용해야 할 때 유용

> ### Super의 예
- 가족 간 호출
    - 부모님(부모 클래스)에게 도움을 요청하거나, 부모님이 만든 유산(기능)을 사용할 때

- 자동차의 기본 기능 확장
    - 기본 자동차(부모 클래스)의 엔진 기능을 유지하면서, 스포츠카(자식 클래스)에서 엔진을 업그레이드

- 회사 업무 분담
    - 회사에서 상사(부모 클래스)의 업무 방식을 따르면서, 자신의 업무를 추가하는 경우

> ### 코드로 보기
1. 부모 클래스의 필드와 메소드 접근
    ```java
    class Animal {
        String name = "동물";

        void sound() {
            System.out.println("동물이 소리를 냅니다.");
        }
    }

    class Dog extends Animal {
        String name = "강아지";

        void sound() {
            super.sound();  // 부모 클래스의 메서드 호출
            System.out.println("멍멍!");
        }

        void printName() {
            System.out.println("부모 이름: " + super.name);  // 부모 클래스의 필드 접근
            System.out.println("자식 이름: " + name);
        }
    }

    public class Main {
        public static void main(String[] args) {
            Dog dog = new Dog();
            dog.sound();
            dog.printName();
        }
    }
    // 출력:
    // 동물이 소리를 냅니다.
    // 멍멍!
    // 부모 이름: 동물
    // 자식 이름: 강아지
    ```

2. 부모 클래스 생성자 호출
- 자식 클래스의 생성자에서 부모 클래스의 생성자를 호출
    ```java
    class Animal {
        Animal(String name) {
            System.out.println("부모 클래스 생성자: " + name);
        }
    }

    class Dog extends Animal {
        Dog(String name) {
            super(name);  // 부모 클래스 생성자 호출
            System.out.println("자식 클래스 생성자: " + name);
        }
    }

    public class Main {
        public static void main(String[] args) {
            Dog dog = new Dog("강아지");
        }
    }
    // 출력:
    // 부모 클래스 생성자: 강아지
    // 자식 클래스 생성자: 강아지
    ```

> ### 쉬운 요약
1. super는 부모 클래스의 멤버에 접근하는 키워드
    - 부모 클래스의 필드, 메소드, 생성자를 사용할 때 사용

2. 주요 역할
    - 부모 클래스의 필드: 자식 클래스와 이름이 같은 필드에 접근
    - 부모 클래스의 메소드: 재정의된 메소드 대신 부모의 메소드 호출
    - 부모 클래스 생성자: 자식 클래스 생성자에서 부모 생성자를 호출

3. super는 반드시 부모와 관련된 작업에만 사용
    - 부모 클래스가 없는 클래스에서는 사용할 수 없음

> ### 비유
1. 부모님에게 도움 요청
    - 자신의 능력(자식 클래스)으로 부족할 때, 부모님(부모 클래스)의 도움을 받음

2. 자동차 기본 기능 사용
    - 스포츠카(자식 클래스)가 고급 기능을 추가하면서, 기본 자동차(부모 클래스)의 엔진 기능도 그대로 활용

3. 회사 업부
    - 회사에서 상사(부모 클래스)가 제공한 기분 틀을 유지하면서, 자신의 방식으로 업무를 확장

[뒤로](java,md)