## Polymorhpism
> ### 다형성이란?
다형성(Polymorhpism)은 같은 이름의 메소드나 객체가 상황에 따라 다른 동작을 수행하는 객체 지향 프로그래밍의 개념</br>
즉, 하나의 인터페이스나 클래스가 여러 가지 형태로 동작할 수 있음을 의미

> ### 다형성의 예
- 스마트폰 버튼
    - 버튼 하나로 전화를 걸 수도, 카메라를 켤 수도 있음

- 동물 울음소리
    - "울다"라는 같은 동작을 실행해도 강아지는 "멍멍", 고양이는 "야옹" 등 다른 소리를 냄

- TV 리모컨
    - 같은 리모컨으로 TV를 켜고, 채널을 바꾸고, 볼륨을 조절

> ### 코드로 보기
1. 메소드 오버라이딩을 통한 다형성
- 부모 클래스의 메소드를 자식 클래스에서 재정의하여 서로 다른 동작을 수행
    ```java
    class Animal {
        void sound() {
            System.out.println("동물이 소리를 냅니다.");
        }
    }

    class Dog extends Animal {
        @Override
        void sound() {
            System.out.println("멍멍!");
        }
    }

    class Cat extends Animal {
        @Override
        void sound() {
            System.out.println("야옹!");
        }
    }

    public class Main {
        public static void main(String[] args) {
            Animal myAnimal;

            myAnimal = new Dog();
            myAnimal.sound();  // 출력: 멍멍!

            myAnimal = new Cat();
            myAnimal.sound();  // 출력: 야옹!
        }
    }
    ```

2. 인터페이스를 사용한 다형성
- 같은 인터페이스를 구현한 클래스가 다양한 방식으로 동작
    ```java
    interface Shape {
        void draw();
    }

    class Circle implements Shape {
        public void draw() {
            System.out.println("원을 그립니다.");
        }
    }

    class Rectangle implements Shape {
        public void draw() {
            System.out.println("사각형을 그립니다.");
        }
    }

    public class Main {
        public static void main(String[] args) {
            Shape myShape;

            myShape = new Circle();
            myShape.draw();  // 출력: 원을 그립니다.

            myShape = new Rectangle();
            myShape.draw();  // 출력: 사각형을 그립니다.
        }
    }
    ```

> ### 쉬운 요약
1. 다형성은 "같은 이름으로 다양한 동작을 수행"하는 객체 지향 프로그래밍의 개념
    - 메소드, 인터페이스, 객체 등이 상황에 따라 다르게 동작

2. 주요 구현 방법
    - 메소드 오버라이딩: 부모 클래스의 메소드를 자식 클래스에서 재정의
    - 인터페이스 구현: 같은 인터페이스를 구현한 클래스가 각기 다른 동작 수행

3. 장점
    - 코드 재사용성: 공통된 인터페이스나 부모 클래스를 기반으로 다양한 객체를 쉽게 확장
    - 유연성: 코드가 상황에 따라 다른 동작을 하도록 설계

> ### 비유
1. 스위스 아미 나이프
    - 하나의 도구로 칼, 가위, 병따개 등 다양한 작업을 수행

2. 동물 울음소리
    - 같은 동작(울다)이라도 동물마다 다른 소리를 냄

3. TV 리모컨
    - 같은 버튼으로 TV를 켜고, 채널을 바꾸고, 볼륨을 조절하는 것처럼 동일한 인터페이스로 여러 기능을 처리

[뒤로](java.md)