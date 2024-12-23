## IO
> ### IO란?
IO(Input/Output)는 컴퓨터와 외부 세계가 대화하는 방법</br>
컴퓨터는 우리와 직접 대화할 수 없기 때문에, 입력(Input)을 통해 데이터를 받고, 출력(Output)을 통해 결과를 전달

- IO는 대화
    - 사람이 질문을 하면(입력), 상대방이 대답을 함(출력)

- IO는 음식 주문
    - 메뉴를 고르고(입력), 주문한 음식을 받음(출력)

> ### IO의 예
1. 입력(Input)
    - 키보드로 텍스트를 입력
    - 파일에서 데이터를 읽어옴
    - 네트워크를 통해 데이터를 받음

2. 출력(Output)
    - 화면에 결과를 출력
    - 파일에 데이터를 저장
    - 네트워크로 데이터를 전송

> ### 코드로 보기
1. 파일에서 읽기
    ```java
    import java.io.FileReader;
    import java.io.IOException;

    public class Main {
        public static void main(String[] args) {
            try (FileReader reader = new FileReader("example.txt")) {
                int character;
                while ((character = reader.read()) != -1) {
                    System.out.print((char) character); // 파일 내용 출력
                }
            } catch (IOException e) {
                e.printStackTrace();
            }
        }
    }
    ```

2. 파일에서 쓰기
    ```java
    import java.io.FileWriter;
    import java.io.IOException;

    public class Main {
        public static void main(String[] args) {
            try (FileWriter writer = new FileWriter("example.txt")) {
                writer.write("Hello, World!"); // 파일에 데이터 저장
            } catch (IOException e) {
                e.printStackTrace();
            }
        }
    }
    ```

> ### 쉬운 요약
1. IO는 "컴퓨터와 데이터를 주고받는 과정"
    - 입력: 데이터를 받는 것(키보드 입력, 파일 읽기 등)
    - 출력: 데이터를 내보내는 것(화면 출력, 파일 쓰기 등)

2. IO는 프로그램과 외부 환경 간의 다리
    - 프로그램이 외부 데이터와 상호작용할 수 있도록 돕는 역할

> ### 비유
1. 대화
    - 질문(Input)을 하고, 대답(Output)을 듣는 과정

2. 주문과 배달
    - 주문을 넣고(입력), 음식을 받는 것(출력)

[뒤로](../README.md#java-study-notes)