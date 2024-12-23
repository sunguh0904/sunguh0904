## Extend
> ### 상속이란?
상속(Extend)은 기존 클래스(부모 클래스)의 속성과 메소드를 다른 클래스(자식 클래스)가 물려받는 것을 의미</br>
상속을 통해 기존 코드를 재사용하고, 필요한 기능을 추가허간 혹장할 수 있음

> ### 상속의 예
- 가족 관계
    - 부모님으로부터 유산(집, 차)을 상속받아 자식이 사용하거나, 자신의 물건을 추가할 수 있음

- 자동차 모델
    - 기본 모델(부모 클래스)을 바탕으로, 스포츠카, 전기차(자식 클래스)를 새롭게 정의

- 도형 그리기
    - 기본 도형(부모 클래스)인 "Shape"을 상속받아 사각형(Rectangle), 원(Circle) 등의 도형을 확장

> ### 코드로 보기
1. 기본 상속 구조
    ```java
    // 부모 클래스
    class Animal {
        void eat() {
            System.out.println("먹는 중...");
        }
    }

    // 자식 클래스
    class Dog extends Animal {
        void bark() {
            System.out.println("멍멍!");
        }
    }

    public class Main {
        public static void main(String[] args) {
            Dog dog = new Dog();
            dog.eat();   // 부모 클래스 메서드 사용
            dog.bark();  // 자식 클래스 메서드 사용
        }
    }
    // 출력:
    // 먹는 중...
    // 멍멍!
    ```

2. 메소드 재정의(오버라이딩)
- 자식 클래스가 부모 클래스의 메소드를 변경할 수 있음
    ```java
    class Animal {
        void sound() {
            System.out.println("소리를 냅니다.");
        }
    }

    class Dog extends Animal {
        @Override
        void sound() {
            System.out.println("멍멍!");
        }
    }

    public class Main {
        public static void main(String[] args) {
            Animal myDog = new Dog();
            myDog.sound();  // 출력: 멍멍!
        }
    }
    ```

> ### 쉬운 요약
1. 상속은 기존 클래스의 속성과 메소드를 물려받아 새로운 클래스를 정의하는 것
    - 코드 재사용성과 확장성을 높임

2. 상속의 키워드
    - 상속: 자식 클래스가 부모 클래스를 상속받을 때 사용

3. 장점
    - 코드 재사용: 공통된 코드를 부모 클래스에 정의해 중복을 줄임
    - 유지보수 용이: 부모 클래스를 수정할면 모든 자식 클래스에 반영
    - 확장성: 자식 클래스에서 부모 클래스의 기능을 추가허거나 변경 가능

> ### 비유
1. 부모-자식 관계
    - 부모로부터 유산(재산)을 물려받아 그대로 사용할 수도 있고, 새롭게 꾸밀 수도 있음

2. 자동차 모델
    - 기본 모델에서 시작해 스포츠카, 전기차 등으로 새롭게 확장

3. 기본 레시피 확장
    - 기본 빵 레시피를 바탕으로 초코빵, 크림빵 만드는 것과 같음

[뒤로](java)