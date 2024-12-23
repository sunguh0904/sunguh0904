## Constaructor
> ### 생성자란?
생성자(Constaructor)는 객체(Object)를 생성할 때 호출되는 특별한 메소드</br>
클래스의 인스턴스가 생성될 때 자동으로 실행되며, 객체의 초기 상태를 설정(초기화)하는 역할을 함

> ### 생성자의 예
- 자동차 공장
    - 자동차를 만들 때, 초기 속도는 0km/h로 설정하고, 새강은 선택값을 설정

- 우유 공장
    - 우유 팩을 만들 때, 기본 크기는 1L, 브랜드 이름을 초기화 함

- 학생 등록
    - 학생 이름과 학번을 입력받아 기본 정보를 설정

> ### 코드로 보기
1. 생성자의 기본 구조
- 생성자의 이름은 클래스 이름과 같아야 하고, 반환 타입이 없음
    ```java
    public class Car {
        String brand;
        int speed;

        // 생성자 정의
        public Car(String brand, int speed) {
            this.brand = brand;  // 필드 초기화
            this.speed = speed;
        }

        public void drive() {
            System.out.println(brand + "가 " + speed + "km/h로 달립니다.");
        }
    }
    ```

2. 생성자 사용
- 객체를 생성할 때, 생성자가 자동으로 호출됨
    ```java
    public class Main {
        public static void main(String[] args) {
            Car myCar = new Car("Hyundai", 100);  // 생성자 호출
            myCar.drive();  // 출력: Hyundai가 100km/h로 달립니다.
        }
    }
    ```

> ### 쉬운 요약
1. 생성자는 객체를 생성하고 초기화하는 메소드
    - 객체를 만들 때 초기값을 설정하거나 초기 동작을 정의

2. 클래스 이름과 같고 반환 타입이 없음
    - 생성자는 `void`조차 명시하지 않고, 반환 타입이 아예 없음

3. 기본 생성자와 사용자의 정의 생성자
    - 기본 생성자: 클래스에 생성자가 없으면 자동으로 제공
    - 사용자 정의 생성자: 필요한 매개변수를 추가하여 초기화 로직을 설정

> ### 비유
1. 붕어빵 기계의 작동 버튼
    - 버튼(생성자)을 눌러 기계를 작동시키고, 재료(매개변수)를 넣어 붕어빵(객체)을 만듦

2. 자동차 공자
    - 공장(클래스)에서 자동차를 만들 때, 색상과 속도 같은 초기값을 설정

3. 학생 등록
    - 새 학생의 이름과 학번을 입력받아 기본 정보를 초기화

[뒤로](../README.md#java-study-notes)