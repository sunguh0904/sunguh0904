## Variable
> ### 변수란?
변수(Variable)는 컴퓨터 안에서 데이터를 담아두는 "상자"라고 생각하면 됨</br>
상자에는 이름이 붙어 있어서, 그 이름으로 상자 안의 내용을 꺼내거나 바꿀 수 있음

비유하자면, 변수는 "라벨이 붙은 상자"</br>
예를 들어, "나이"라는 이름표가 붙은 상자에 20이라는 숫자를 담아 두었다면, 우리는 "나이"라는 이름으로 그 값을 계속 불러올 수 있음

> ### 변수의 예
- 노트에 적는 정보
    - "나이: 20", "이름: 홍길동"처럼 값을 저장하고 나중에 다시 꺼낼 수 있는 기록 공간

- 택배 상자
    - "주소"라는 이름표가 붙은 상자에서 "서울"이라는 내용을 담아두고, 필요할 때 다시 확인하는 느낌

> ### 코드로 보기
1. 숫자를 저장하는 변수
- 숫자 20을 변수 age에 담음
    ```java
    int age = 20; // 변수 "age"에 20을 저장
    ```

2. 이름을 저장하는 변수
- 문자열 "홍길동"을 변수 name에 담음
    ```java
    String name = "홍길동"; // 변수 "name"에 "홍길동"을 저장
    ```

3. 참/거짓을 저장하는 변수
- 참(true)을 변수 isStudent에 담음
    ```java
    boolean isStudent = true; // 변수 "isStudent"에 true를 저장
    ```

> ### 쉬운 요약
1. 변수는 "값을 담아두는 이름표가 붙은 상자"
    - 상자에 값을 넣고, 이름으로 찾아서 값을 사용할 수 있음
    - 예: "age"라는 상자에 20을 넣고, 언제든 "age"를 열어서 값을 꺼냄

2. 변수는 프로그램에서 데ㅣ터를 저장하고 활용하기 위한 기본 도구
    - 프로그램에서 실행 중에 데이터를 담아두고 필요할 때 꺼내 쓰는 역할을 함

3. 변수는 이름으로 데이터를 관리
    - 이름(age, name)으로 값(20, "홍길동")을 저장하거나 불러옴

> ### 비유
1. 변수는 라벨이 붙은 택배 상자
    - "주소"라는 상자에 "서울"을 넣고, "주소"를 부르면 "서울"이라는 값을 꺼낼 수 있음
        ```java
        String address = "서울";
        ```

2. 변수는 노트의 칸
    - "나이: 20"처럼 정보를 기록하는 칸을 떠올리면 됨
        ```java
        int age = 20;
        ```

3. 변수는 계산기의 메모리 기능
    - 계산기에서 숫자를 저장하고 나중에 불러오듯, 변수는 데이터를 저장하고 활용함

[뒤로](java.md)