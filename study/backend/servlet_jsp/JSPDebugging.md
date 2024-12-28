## JSP 디버깅
> ### JSP 오류 종류
JSP 디버깅을 위해서는 발생하는 오류의 종류를 이해하는 것이 중요

#### 1. Translation Time Error
- 발생 시점: JSP → Java Translation 시점
- 설명: JSP 파일을 Java 파일로 변환하면서 발생하는 오류
- 원인: Web Container가 JSP 페이지의 Scripting elements의 구문을 분석할 수 없을 때 발생
- 예시: 여는 태그만 있고 닫는 태그가 없는 경우
    ```jsp
    <%! // 여는 태그만 있고 닫는 태그가 없음
    ```

#### 2. Compile Time Error
- 발생 시점: Java 파일을 Class 파일로 컴파일 할 때
- 설명: Java 코드의 문제로, Java 문법 오류
- 원인: 스크립틀릿 태그 내부 코드 오류
- 예시: 자바 문장을 끝낼 때, ‘;’ 사용하지 않은 경우
    ```jsp
    <% int number = 10 // 세미콜론이 없음
    ```

#### 3. Runtime Error
- 발생 시점: 실행 도중
- 설명: 실행 시의 에러로 NullPointerException 등이 발생
- 원인: HTML form 태그 전송 시 없는 이름을 getParameter() 인자에 사용하면 발생
- 예시: getParameter()는 null을 반환하는데 이 값을 가지고 조작하는 경우
    ```jsp
    <%
        String value = request.getParameter("nonexistent");
        int length = value.length(); // NullPointerException 발생 가능
    %>
    ```

> ### 주요 기능
1. **오류 종류 이해**: JSP 디버깅을 위해 발생하는 오류의 종류를 이해할 수 있음
2. **오류 원인 파악**: 각 오류의 원인을 파악하여 문제를 해결할 수 있음

> ### 왜 사용해야 하는가?
1. **효율적인 디버깅**: 오류의 종류와 원인을 이해하면 효율적으로 디버깅할 수 있음
2. **안정성 향상**: 오류를 사전에 파악하고 해결하여 애플리케이션의 안정성을 높일 수 있음

> ### 쉬운 요약
1. JSP 디버깅은 "JSP 페이지에서 발생하는 오류를 이해하고 해결하는 과정"
    - Translation Time Error, Compile Time Error, Runtime Error의 종류와 원인을 이해

> ### 비유
1. 문제 해결사
    - JSP 디버깅은 "문제 해결사"와 같음
    - 예: 문제의 원인을 파악하고 해결하는 과정

2. 탐정
    - JSP 디버깅은 "탐정"과 같음
    - 예: 단서를 찾아 문제의 원인을 파악하고 해결

[뒤로](./ServletJSP.md)
