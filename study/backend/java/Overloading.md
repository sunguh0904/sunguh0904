## Overloading
> ### 오버로딩이란?
오버로딩(Overloading)은 같은 이름의 메소드를 여러 개 정의하되, 매개변수의 유형이나 개수를 다르게 설정하여 구분하는 방법</br>
즉, 하나의 이름으로 다양한 동작을 수행할 수 있도록 메소드를 설계하는 기법

> ### 오버로딩의 예
- 문 열기
    - 손잡이를 돌려 열기, 버튼을 눌러 열기, 키를 사용해 열기 등 방법은 다르지만 결과는 문을 여는 것

- 계산기
    - 숫자 두 개르 더하기(덧셈), 숫자 세 개를 더하기(덧셈), 문자열을 더해 연결하기(문자열 연결)

- 주문하기
    - 한 개의 음식을 주문하기, 두 개 이상의 음식을 주문하기, 특정 옵션을 추가해서 주문하기

> ### 코드로 보기
1. 오버로딩된 메소드
    ```java
    public class OverloadingExample {
        // 두 정수를 더함
        public int add(int a, int b) {
            return a + b;
        }

        // 세 정수를 더함
        public int add(int a, int b, int c) {
            return a + b + c;
        }

        // 두 실수를 더함
        public double add(double a, double b) {
            return a + b;
        }
    }
    ```

2. 메소드 호출
    ```java
    public class Main {
        public static void main(String[] args) {
            OverloadingExample example = new OverloadingExample();

            // 호출되는 메서드가 매개변수에 따라 달라짐
            System.out.println(example.add(2, 3));          // 출력: 5 (int add(int, int))
            System.out.println(example.add(1, 2, 3));      // 출력: 6 (int add(int, int, int))
            System.out.println(example.add(2.5, 3.5));     // 출력: 6.0 (double add(double, double))
        }
    }
    ```

> ### 쉬운 요약
1. 오버로딩은 같은 이름의 메소드를 파라미터에 따라 다르게 정의하는 것
    - 메소드 이름은 같지만, 파라미터의 개수, 타입, 순서로 구분

2. 메소드 선택은 컴파일 시점에 결정
    - 호출할 때 전달한 인수에 따라 적절한 메소드가 선택됨

3. 장점
    - 코드 가독성을 높이고, 같은 이름으로 다양한 작업을 수행할 수 있음

> ### 비유
1. 다용도 도구(스위스 아미 나이프)
    - 하나의 도구로 병을 따거나 칼로 자르거나 가위로 자르는 등 여러 작업을 처리할 수 있음

2. 전화를 거는 방법
    - 전화번호를 입력해서 걸기, 연락처에서 선택해서 걸기, 음성으로 "엄마에게 전화"라고 말하기 등 다양한 방식으로 같은 결과를 얻음

[뒤로](java,md)