## String
> ### String이란?
String은 문자열을 다루는 데이터 타입으로, 문자의 집합을 의미</br>
자바에서 String 클래스는 문자를 저장하고 조작하기 위한 다양한 메소드를 제공</br>
String은 문자 하나(char)를 여러 개 묶어서 하나의 단위로 다루는 데 사용

> ### String의 예
- 이름: "John Doe"
- 전화번호: "010-1234-5678"
- 주소: "서울특별시 강남구 테헤란로 123"
- 문장: "Hello, World!"

> ### 코드로 보기
1. 문자열 선언
    ```java
    public class Main {
        public static void main(String[] args) {
            String greeting = "Hello, World!";  // 문자열 선언 및 초기화
            System.out.println(greeting);      // 출력: Hello, World!
        }
    }
    ```

2. 문자열 메소드 사용
    ```java
    public class Main {
        public static void main(String[] args) {
            String text = "Hello, Java!";
            
            // 문자열 길이
            System.out.println(text.length());  // 출력: 12

            // 특정 문자 추출
            System.out.println(text.charAt(0));  // 출력: H

            // 부분 문자열 추출
            System.out.println(text.substring(7));  // 출력: Java!

            // 문자열 비교
            System.out.println(text.equals("Hello, Java!"));  // 출력: true

            // 문자열 합치기
            System.out.println(text + " Let's code!");  // 출력: Hello, Java! Let's code!
        }
    }
    ```

> ### 쉬운 요약
1. String은 문자들의 모임으로, 단어, 문자 등을 표현하는 데 사용
    - 문자열은 변경이 불가능(Immutable)
    - 새로운 값을 할당하면 새 객체가 생성

2. 다양한 메소드 제공
    - 문자열 조작, 검색, 비교, 변환 등을 간편하게 처리할 수 있음

> ### 비유
1. String은 문자의 배열
    - String은 단어를 구성하는 알파벳의 배열과 같으며, "문자를 차례대로 나열한 모음"

2. String은 문서의 줄
    - 여러 문장을 줄 단위로 나열해 문서를 구성하듯, String은 문자를 나열해 데이터를 구성

3. String은 편지
    - 편지 내용이 변경되면 새 편지를 써야 하는 것처럼, String도 변경 불가능하며 새로운 문자열을 생성

[뒤로](java)