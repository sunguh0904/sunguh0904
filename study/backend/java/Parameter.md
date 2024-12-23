## Parameter
> ### 파라미터란?
파라미터(Parameter)는 메소드(함수) 호출 시 메소드에 전달되는 값(인수)을 받아 처리하는 변수</br>
즉, 메소드가 외부로부터 데이터를 입력받아 작업을 수행할 수 있도록 도와주는 역할

> ### 파라미터의 예
- 요리 레시피
    - "감자와 당근을 넣으면 감자당근볶음이 되고, 돼지고기를 넣으면 돼지고기볶음이 된다"

- 택배 배송
    - 태갭 상자에 주소(파라미터)를 적으면, 택배는 해당 주소로 배달

- 계산기
    - 숫자 두 개를 입력받아 더하거나 빼는 작업을 수행

> ### 코드로 보기
1. 파라미터가 있는 메소드
    ```java
    public class ParameterExample {
        // 두 숫자의 합을 구하는 메서드
        public int add(int a, int b) {
            return a + b;
        }

        public static void main(String[] args) {
            ParameterExample example = new ParameterExample();
            int result = example.add(5, 3);  // 5와 3은 파라미터로 전달됨
            System.out.println("결과: " + result);  // 출력: 결과: 8
        }
    }
    ```

2. 파라미터가 여러 개인 메소드
    ```java
    public void printMessage(String message, int repeatCount) {
        for (int i = 0; i < repeatCount; i++) {
            System.out.println(message);
        }
    }

    // 호출 예:
    printMessage("Hello, World!", 3);
    // 출력:
    // Hello, World!
    // Hello, World!
    // Hello, World!
    ```

3. 파라미터가 없는 메소드
- 파라미터가 없는 메소드는 정해진 동작만 수행
    ```java
    public void printHello() {
        System.out.println("Hello!");
    }

    // 호출 예:
    printHello();  // 출력: Hello!
    ```

> ### 쉬운 요약
1. 파라미턴ㄴ 메소드가 외부 데이터를 입력받을 수 있도록 정의된 변수
    - 메소드 호출 시, 데이터를 전달하여 작업을 수행할 수 있게 함

2. 파라미터와 인수
    - 파라미터: 메소드 선언부에서 정의된 변수
    - 인수: 메소드를 호출할 때 전달하는 실제 값

3. 파라미터는 메소드의 입력값
    - 메소드가 다른 작업을 하도록 입력 데이터를 제공

> ### 비유
1. 요리 레시피
    - 레시피(메소드)에서 재료(파라미터)를 받아 요리를 만듦
    - 감자와 당근 -> 감자당근볶음, 돼지고기 -> 돼지고기볶음

2. 택배 배송
    - 택배 상자에 주소(파라미터)를 적으면 택배가 해당 주소로 배송

3. 계산기 입력
    - 계산기(메소드)에 숫자 두 개(파라미터)를 입력하면 덧셈 결과를 제공

[뒤로](java.md)