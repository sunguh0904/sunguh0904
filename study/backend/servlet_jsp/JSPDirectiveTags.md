## JSP 지시자 태그
> ### page 지시자 태그 사용법
여러 개의 page 구문을 사용할 수 있지만, import 속성을 제외하고는 한 페이지에 한 번씩만 선언할 수 있음</br>
page 지시어는 JSP 파일의 어느 위치에 와도 상관 없으나, 가장 첫 부분에 사용하는 것이 좋음

```jsp
<%@ page import="java.io.*" %> <!-- java.io 패키지 import -->
<%@ page contentType="text/html" %> <!-- MIME 타입 설정 -->
```

> ### JSP 지시자 태그 종류
1. **import**
    - 변환될 Servlet class에 필요한 Java class의 import문을 정의
    - `java.lang`, `javax.servlet`, `javax.servlet.http`, `javax.servlet.jsp`는 기본적으로 import 되어 있음
    - 여러 package import 시 ‘,’ 기호를 이용하여 구분
    ```jsp
    <%@ page import="java.io.*" %> <!-- java.io 패키지 import -->
    <%@ page import="java.util.*, java.sql.*" %> <!-- java.util, java.sql 패키지 import -->
    ```

2. **contentType**
    - MIME 타입과 문자 인코딩을 설정
    ```jsp
    <%@ page contentType="text/html;charset=euc-kr" %> <!-- MIME 타입과 문자 인코딩 설정 -->
    ```

3. **isErrorPage**
    - 현재 페이지가 JSP 오류 처리용 페이지인지 정의하며, 값은 true 또는 false(= default)
    - true이면, exception 내장 객체를 사용할 수 있음
    ```jsp
    <%@ page isErrorPage="true" %> <!-- 오류 처리용 페이지 설정 -->
    ```

4. **errorPage**
    - 해당 JSP 페이지가 발생시키는 모든 runtime exception을 처리할 다른 JSP 페이지를 지정
    - 값은 상대적인 URL
    ```jsp
    <%@ page errorPage="/error/errorForm.jsp" %> <!-- 오류 처리 페이지 설정 -->
    ```

5. **include 지시자 태그**
    - include 지시자 태그를 사용하면 다른 페이지(JSP, HTML)를 포함할 수 있음
    - 문법: `<%@ include file="페이지 경로" %>`
    ```jsp
    <%@ include file="footer.html" %> <!-- 다른 페이지 포함 -->
    ```

> ### 주요 기능
1. **페이지 설정**: JSP 페이지의 설정을 정의할 수 있음
2. **오류 처리**: 오류 처리 페이지를 지정할 수 있음
3. **포함**: 다른 페이지를 포함하여 재사용성을 높일 수 있음

> ### 왜 사용해야 하는가?
1. **유연성**: JSP 페이지의 설정을 유연하게 정의할 수 있음
2. **재사용성**: 다른 페이지를 포함하여 코드의 재사용성을 높일 수 있음
3. **유지보수 용이**: 설정을 한 곳에서 관리하여 유지보수가 용이함

> ### 쉬운 요약
1. JSP 지시자 태그는 "JSP 페이지의 설정을 정의하는 태그"
    - 페이지 설정, 오류 처리, 포함 기능을 제공

> ### 비유
1. 설정 파일
    - JSP 지시자 태그는 "프로그램의 설정 파일"과 같음
    - 예: 프로그램의 설정을 정의하고 관리하는 파일

2. 레고 블록
    - JSP 지시자 태그는 "레고 블록을 조립하는 과정"과 같음
    - 예: 레고 블록을 조립하여 하나의 완성된 작품을 만드는 과정

[뒤로](./ServletJSP.md)
