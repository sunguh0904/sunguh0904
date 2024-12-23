## Exception
> ### Exception이란?
예외(Exception)는 프로그램 실행 중에 발생하는 예상치 못한 문제를 의미</br>
쉽게 말해, "갑자기 길을 막고 있는 돌멩이"와 같은 상황</br>
프로그램이 정상적으로 실행되다가 예상치 못한 입력이나 상황을 만나면 "예외(Exception)"가 발생

> ### Exception의 예
1. 일상에서의 예
    - ATM기기 사용
    "잔액 부족"이 발생하면 돈을 출금할 수 없음

    - 택배 배송
    주소가 잘못 입력된 경우, 택배가 배달되지 않고 중단

2. 프로그램에서의 예
    - 숫자를 0으로 나눌 때
        ```java
        int result = 10 / 0; // ArithmeticException 발생
        ```

    - 없는 파일을 읽을 때
        ```java
        File file = new File("nonexistent.txt");
        Scanner scanner = new Scanner(file); // FileNotFoundException 발생
        ```

> ### 코드로 보기
1. 예외 발생과 처리
    ```java
    public class Main {
        public static void main(String[] args) {
            try {
                int result = 10 / 0; // 예외 발생
            } catch (ArithmeticException e) {
                System.out.println("0으로 나눌 수 없습니다."); // 예외 처리
            }
        }
    }
    ```

2. 파일 읽기 예외 처리
    ```java
    import java.io.File;
    import java.io.FileNotFoundException;
    import java.util.Scanner;

    public class Main {
        public static void main(String[] args) {
            try {
                File file = new File("nonexistent.txt");
                Scanner scanner = new Scanner(file); // 예외 발생
            } catch (FileNotFoundException e) {
                System.out.println("파일을 찾을 수 없습니다."); // 예외 처리
            }
        }
    }
    ```

> ### 쉬운 요약
1. Exception은 프로그램 실행 중에 발생하는 문제
    - 예를 들어, 잘못된 입력이나 외부 환경의 문제로 인해 프로그램이 멈추는 상황

2. 예외 처리를 통해 문제를 해결하고 프로그램을 계속 실행
    - 예외가 발생하더라도 적절한 처리를 통해 프로그램을 멈추지 않도록 설계

> ### 비유
1. 도로 위 돌멩이
    - 차가 도로에서 돌멩이를 만나면 멈춤(예외 발생)
    - 돌맹이를 치우면(예외 처리) 다시 갈 수 있음

2. 전화 연결 문제
    - 전화를 걸었는데 "통화 중"이면 연결이 되지 않습니다(예외 발생)
    - 다음에 다시 걸면 연결됩니다(문제 해결)

[뒤로](../README.md#java-study-notes)