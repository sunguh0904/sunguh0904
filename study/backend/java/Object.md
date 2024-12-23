## Object
> ### Object란?
객체(Object)는 클래스를 기반으로 생성된 실체로, 데이터(필드)와 동작(메소드)을 포함하는 프로그래밍의 기본 구성 요소</br>
- 객체는 "현실 세계의 사물을 프로그램으로 표현한 것"
- 클래스는 객체의 설계도이고, 객체는 이 설계도로 만들어진 실체

> ### Object의 예
- 자동차
    - 데이터: 브랜드, 색상, 속도
    - 동작: 가속, 브레이크, 방향 전환

- 학생
    - 데이터: 이름, 학번, 학년
    - 동작: 공부하다, 질문하다, 졸업하다

- 스마트폰
    - 데이터: 제조사, 모델명, 베터리 잔량
    - 동작: 전화 걸기, 메시지 보내기, 사진 찍기

> ### 코드로 보기
1. 객체 생성
    ```java
    class Car {
        String brand;
        int speed;

        void drive() {
            System.out.println(brand + "가 " + speed + "km/h로 달립니다.");
        }
    }

    public class Main {
        public static void main(String[] args) {
            Car myCar = new Car();  // 객체 생성
            myCar.brand = "Hyundai";  // 데이터 설정
            myCar.speed = 120;
            myCar.drive();  // 동작 실행
        }
    }
    ```

2. 다수의 객체
    ```java
    public class Main {
        public static void main(String[] args) {
            Car car1 = new Car();
            car1.brand = "Hyundai";
            car1.speed = 100;

            Car car2 = new Car();
            car2.brand = "Toyota";
            car2.speed = 80;

            car1.drive();  // 출력: Hyundai가 100km/h로 달립니다.
            car2.drive();  // 출력: Toyota가 80km/h로 달립니다.
        }
    }
    ```

> ### 쉬운 요약
1. 객체는 클래스를 기반으로 생성된 실체
    - 데이터를 저장하고, 동작을 실행하는 프로그램의 기본 단위

2. 구성 요소
    - 데이터: 객체가 가진 상태(속성)
    - 동작: 객체가 수행할 수 있는 기능(메소드)

3. 객체는 현실 세계의 사물을 코드로 표현한 것
    - 예: 자동차, 학생, 스마트폰

> ### 비유
1. 붕어빵과 붕어빵 틀
    - 클래스는 붕어빵 틀이고, 객체는 틀로 찍어낸 실제 붕어빵

2. 집과 설계도
    - 클래스는 집의 설계도이고, 객체는 설계도를 기반으로 지어진 실제 집

3. 자동차와 모델
    - 자동차 모델(클래스)은 설계이고, 각 자동차(객체)는 이 설계를 기반으로 만들어진 개별 제품

[뒤로](java.md)