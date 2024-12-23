## Class
> ### 클래스란?
클래스(Class)는 객체(Object)를 만들기 위한 설계도</br>
어떤 데이터를 담고, 어떤 동작을 수행할 수 있는지를 정의함</br>
객체는 이 설계도를 기반으로 만들어진 실제 데이터와 행동을 가진 실체

> ### 클래스의 예
- 붕어빵 틀
	- 틀(클래스)을 기준으로 만들어진 붕어빵(객체)이 여러 개 있을 수 있음

- 청사진
	- 집을 짓기 위한 설계도(클래스)를 기준으로 여러 채의 집(객체)을 지음

- 자동차 공장
	- 자동차 모델(클래스)은 동일하지만, 실제 생산된 자동차(객체)는 각각 고유의 색상과 번호를 가질 수 있음

> ### 코드로 보기
1. 클래스 정의
    ```java
    // 클래스 정의
    public class Car {
        // 속성 (필드)
        String brand;
        int speed;

        // 동작 (메소드)
        public void drive() {
            System.out.println(brand + "가 " + speed + "km/h로 달립니다.");
        }
    }
    ```

2. 객체 생성
    ```java
    public class Main {
        public static void main(String[] args) {
            // Car 클래스의 객체 생성
            Car myCar = new Car();
            myCar.brand = "Hyundai"; // 속성 값 설정
            myCar.speed = 100;       // 속성 값 설정
            myCar.drive();           // 동작 수행
            // 출력: Hyundai가 100km/h로 달립니다.
        }
    }
    ```

> ### 쉬운 요약
1. 클래스는 객체를 만들기 위한 설계도
	- 객체가 가질 데이터(속성)와 할 수 있는 동작(메소드)을 정의

2. 객체는 클래스의 실체
	- 클래스라는 설계도로 실제 만들어진 결과물이 객체

3. 클래스와 객체의 관계
	- 클래스는 붕어빵 틀이고, 객체는 그 틀로 찍어낸 붕어빵

> ### 비유
1. 붕어빵 틀과 붕어빵
	- 붕어빵 틀(클래스)은 “어떤 모양과 속성으로 만들지”를 정의하고, 실제 붕어빵(객체)은 그 정의대로 만들어진 결과물

2. 청사진과 집
    - 청사진(클래스)은 “집의 구조와 디자인”을 정의하고, 실제 집(객체)은 그 청사진을 기반으로 지어진 실물

3. 자동차 모델과 실제 자동차
	- 자동차 모델 설계도(클래스)를 기준으로 다양한 색상과 옵션을 가진 자동차(객체)를 생산

[뒤로](java.md)