## JSP Elements
> ### JSP Element 표기법
JSP Elements는 JSP 페이지에서 다양한 기능을 수행하기 위해 사용되는 태그

#### JSP Element 표기법
- Comments tag: `<%-- 주석 --%>`
- Directive tag: `<%@ 지시자 %>`
- Declaration tag: `<%! 선언문 %>`
- Scriptlet tag: `<% 코드 %>`
- Expression tag: `<%= 표현식 %>`

#### 참고
- directive 필드: 최상단 지시자 태그
- declare: 선언 태그
- comment: 주석 태그

> ### JSP Element 표기법 예제
#### Comments tag 종류에 따른 컴파일 여부
- HTML 주석: 내부에서 `out.write();`로 변환되나 화면에는 보이지 않음
    ```html
    <!-- HTML 주석입니다 -->
    ```
    ```java
    out.write("<!-- HTML 주석입니다 --> \r\n");
    ```

- JSP 주석 태그: JSP 파일 내에만 존재하고, Servlet 코드에는 포함되지 않음
    ```jsp
    <%-- JSP 주석 태그 입니다. --%>
    ```

- Java 주석 태그: 변환된 Servlet 코드에는 포함되지만 HTTP 응답으로 전송되지 않음
    ```jsp
    <%-- //Java 주석입니다. --%>
    //Java 주석입니다
    ```

> ### Directive tag
JSP 페이지 전체에 영향을 미치는 정보를 기술할 때 사용
```jsp
<%@ 지시자 [속성명='value'] … %>
```
- 지시자 종류: `page`, `include`, `taglib`
    ```jsp
    <%@ page import="java.io.*" %>
    <%@ include file="header.html" %>
    <%@ taglib uri="/WEB-INF/tags/abc" prefix="abc" %>
    ```

> ### Declaration tag
Servlet 클래스의 멤버 변수/method에 해당하는 코드를 작성할 때 사용
- 멤버 변수 선언
    ```jsp
    <%! public static final String DEFAULT_NAME = "홍길동"; %>
    <%! int counter = 0; %>
    ```

- 멤버 method 선언
    ```jsp
    <%! 
    public String getName(HttpServletRequest request) {
        return request.getParameter("name");
    }
    %>
    ```

> ### Scriptlet tag
`_jspService` 메서드의 로컬 변수와 코드를 작성할 때 사용
- 로컬 변수 선언
    ```jsp
    <% int i = 0; %>
    ```

- Java code 내용 기술
    ```jsp
    <% if (i > 10) { %>
        i가 10보다 큽니다.
    <% } else { %>
        i가 10보다 작습니다.
    <% } %>
    ```

> ### Expression tag
Servlet 코드에서 `out.print()`의 역할을 수행
- 예시
    ```jsp
    현재 시간은 <%= new java.util.Date() %> 입니다.
    ```

- 스크립트
    ```jsp
    <%= new java.util.Date(); %>
    ```
    - Servlet 변환
        ```java
        out.print(new java.util.Date(););
        ```
        - Syntax Error 발생

> ### JSP와 Servlet
JSP 컴파일 시 Servlet으로 변환되어 서비스됨</br>
컴파일 변환 과정을 확인하는 방법:
1. `web/META-INF/` 경로에 `context.xml` 파일 생성
2. `context.xml` 파일에 다음과 같이 기록
    ```xml
    <Context workDir="WEB-INF/work" />
    ```
    - `context.xml`은 웹 애플리케이션 서버에서 사용할 자원을 설정하는 파일
    - `Context workDir` 속성은 컴파일 된 JSP class 파일이 위치할 경로를 가리킴

3. 설정이 끝나면 서버를 재실행하고 Project Explorer를 갱신하여 생성된 소스코드를 확인
4. JSP Elements - Java 코드 변환 내용을 확인 (JSP 주석 태그는 컴파일 시 포함되지 않음)

[뒤로](JSP.md)
