## JSP Exception 처리
> ### JSP의 예외 처리
JSP 페이지에서 발생하는 Exception을 처리하기 위해 별도의 예외 처리 페이지를 지정</br>
하나의 JSP 페이지에 대한 예외 처리 페이지는 하나만 지정할 수 있으므로 예외마다 다른 예외 처리는 불가능

#### 예외가 발생할 페이지의 코드
```jsp
<%@ page errorPage="/error/exceptionPage.jsp" %> <!-- 예외 처리 페이지 지정 -->
```

#### 예외를 처리할 페이지의 코드
```jsp
<%@ page isErrorPage="true" %> <!-- 예외 처리 페이지 설정 -->
<%
    // 예외 객체를 사용하여 예외 정보 출력
    out.println("Exception: " + exception.getMessage());
%>
```

> ### 주요 기능
1. **예외 처리 페이지 지정**: JSP 페이지에서 발생하는 예외를 처리할 페이지를 지정할 수 있음
2. **예외 정보 출력**: 예외 처리 페이지에서 예외 정보를 출력할 수 있음

> ### 왜 사용해야 하는가?
1. **안정성**: 예외 발생 시 사용자에게 친절한 메시지를 제공하여 애플리케이션의 안정성을 높일 수 있음
2. **유지보수 용이**: 예외 처리를 중앙화하여 유지보수가 용이함

> ### 쉬운 요약
1. JSP Exception 처리는 "JSP 페이지에서 발생하는 예외를 처리하는 방법"
    - 예외 처리 페이지를 지정하고, 예외 정보를 출력할 수 있음

> ### 비유
1. 안전망
    - JSP Exception 처리는 "안전망"과 같음
    - 예: 문제가 발생했을 때 안전망이 있어 큰 사고를 방지

2. 고객 서비스 센터
    - JSP Exception 처리는 "고객 서비스 센터"와 같음
    - 예: 문제가 발생했을 때 고객 서비스 센터가 문제를 해결

[뒤로](./ServletJSP.md)
