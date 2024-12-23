## Method
> ### 메소드란?
메소드(Method)는 특정 작업을 수행하는 코드의 묶음</br>
한 번 정의해두면 언제든지 호출하여 사용할 수 있는, 프로그램의 작은 도구라고 할 수 있음

비유하자면, 메소드는 "요리 레시피"와 같음
- 레시피에는 재료(입력값)와 요리 방법(로직)이 적혀 있으며, 결과물(출력값)을 만들어 냄
- 예를 들어, "김치찌개를 만들기"라는 레시피를 메소드로 정의하면, 재료만 주어지면 언제든지 김치찌개를 만들 수 있음

> ### 메소드의 예
- 커피 만들기
    - 메소드 이름: makeCoffee
    - 입력값: "커피 원두", "물"
    - 출력값: "커파"

- 계산기 더하기
    - 메소드 이름: add
    - 입력값: 2, 3
    - 출력값: 5

> ### 코드로 보기
1. 메소드 정의와 호출
    - 메소드 정의
        ```java
            public static int add(int a, int b) {
                return a + b;  // 두 숫자의 합을 반환
            }
        ```

    - 메소드 호출
        ```java
            public static void main(String[] args) {
                int result = add(2, 3);  // 메소드 호출
                System.out.println(result);  // 출력: 5
            }
        ```

2. 문자열 출력 메소드
    ```java
    public static void printMessage(String message) {
        System.out.println(message);
    }

    // 호출 예:
    printMessage("Hello, World!");  // 출력: Hello, World!
    ```

> ### 쉬운 요약
1.	메소드는 특정 작업을 수행하는 코드의 묶음
	- 한 번 만들어두면 필요할 때마다 호출하여 사용할 수 있음

2.	메소드는 재료(입력값)를 받아 결과물(출력값)을 반환
	- 입력값 → 메소드 로직 → 출력값

3.	코드를 효율적으로 관리하고 재사용성을 높여줌
	- 반복적인 작업을 줄이고, 코드가 더 깔끔해짐

> ### 비유
1.	요리 레시피
	- 김치찌개를 만드는 방법을 정의해두면, 재료만 바꿔서 언제든지 같은 방식으로 요리를 만들 수 있음
	- 예: makeSoup(김치, 돼지고기) → 김치찌개, makeSoup(미역, 소고기) → 미역국

2.	계산기 버튼
	- 계산기의 “더하기” 버튼을 누르면 입력값(숫자 두 개)을 받아 합을 출력함
	- 예: add(2, 3) → 5

3.	공장 생산 라인
    - 메소드는 공장에서 작업을 수행하는 라인과 같아서, 입력(재료)을 주면 정해진 과정으로 출력(결과)을 만들어 냄

[뒤로](java.md)