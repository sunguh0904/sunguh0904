## Servlet Lifecycle
> ### Servlet 개요
Servlet은 Server + Applet의 합성어로, JAVA 언어를 이용하여 사용자의 요청을 받아 처리하고 처리 결과를 다시 사용자에게 전송하는 역할의 Class 파일</br>
웹에서 동적인 페이지를 Java로 구현한 서버측 프로그램

> ### Servlet 역사
Java 언어의 창시자인 제임스 고슬링(James Gosling)은 1995년 자바를 발표하며 자바로 구현할 수 있는 서버 프로그래밍 기술에 대해서도 염두에 두고 있었지만, 해당 개념이 실제 구현이 가능한 정도로 제품화 되지 않은 상태였음</br>
얼마 뒤, Java 팀의 일원이었던 파바니 디완지(Pavni Diwanji)는 자바 서버 기술에 대한 필요성을 느껴 Servlet 개념을 고안하였고, 이 개념을 토대로 프로젝트를 진행하여 Servlet 구현 및 제품화에 성공</br>
이 기술은 1997년 6월에 Servlet 1.0을 공식 발표하면서 Java EE의 제품화에 포함됨

> ### Servlet 설계 규약
1. 모든 Servlet은 `javax.servlet.Servlet` 인터페이스를 상속 받아 구현
2. Servlet 구현 시 `Servlet` 인터페이스와 `ServletConfig` 인터페이스를 `javax.servlet.GenericServlet`에 구현
3. HTTP 프로토콜을 사용하는 Servlet은 `HttpServlet` 클래스를 상속 받음 (`javax.servlet.http.HttpServlet` 클래스는 `javax.servlet.GenericServlet`을 상속받은 클래스)
4. Servlet의 Exception을 처리하기 위해서는 `javax.servlet.ServletException`을 상속 받아야 함

> ### Servlet 동작 구조
Servlet의 동작 구조는 다음과 같음
1. 첫 요청이면, 객체를 생성하며 `init()` 메서드를 호출
2. 이후 작업이 실행될 때마다 `service()` 메서드가 요청한 HTTP 타입에 따라 `doGet()`, `doPost()` 메서드를 호출
3. 최종적으로 Servlet이 서비스 되지 않을 때 `destroy()` 메서드가 호출됨

> ### Servlet Container란
웹 서버 또는 응용 프로그램 서버의 일부로, 웹 서버에서 온 요청을 받아 Servlet 클래스를 관리하는 역할(= 생명 주기 관리)을 함</br>
Servlet에 대한 Container 설정은 Deployment Descriptor(`web.xml`) 파일을 이용

> ### Deployment Descriptor(DD)
배포서술자는 Application에 대한 전체 설정 정보를 가지고 있는 파일로, XML 형식 파일이며 요소(= 태그)로 이루어져 있음</br>
파일 내 설정 정보를 가지고 웹 컨테이너가 Servlet을 구동

설정 정보:
- Servlet 정의 및 Servlet 초기화 파라미터
- Session 설정 파라미터
- Servlet-JSP 매핑 및 MIME 타입 매핑
- 보안 설정
- Welcome 파일 리스트 설정
- Error 페이지 리스트, 리소스, 환경변수

위치: Application 폴더 > WEB-INF 폴더 > `web.xml` 파일

> ### Servlet mapping
Servlet 매핑은 클라이언트가 Servlet에 접근할 때 원본 클래스명이 아닌 다른 명칭으로 접근할 수 있게 함</br>
별칭 사용 설정 방법은 `web.xml`을 이용한 적용과 `@annotation`으로 두 가지 방법이 있음

#### web.xml 이용
```xml
<servlet>
    <servlet-name>mapping명칭</servlet-name>
    <servlet-class>실제 클래스명</servlet-class>
</servlet>
<servlet-mapping>
    <servlet-name>mapping명칭</servlet-name>
    <url-pattern>사용자 접근명칭</url-pattern>
</servlet-mapping>
```

#### @annotation 이용
```java
@WebServlet("/mapping명칭")
public class Servlet명 extends HttpServlet {
    // Servlet code
}
```

> ### Servlet 초기값 설정
Servlet 초기값 설정은 `ServletConfig`와 `ServletContext`를 통해 이루어짐

#### ServletConfig
`web.xml`의 정보를 가져와 저장한 인터페이스 객체로, `getServletConfig()` 메서드로 정보가 저장된 객체를 호출할 수 있음</br>
`getInitParameter("저장명")`으로 초기화된 값을 가져올 수 있음</br>
지정된 Servlet에서만 활용 가능한 초기값이며, 동적 수정이 불가한 상수값</br>
Servlet이 초기화된 이후에 활용 가능

```xml
<web-app>
    <servlet>
        <servlet-name>mapping명</servlet-name>
        <servlet-class>설정 Class명</servlet-class>
        <init-param>
            <param-name>저장명</param-name>
            <param-value>저장값</param-value>
        </init-param>
    </servlet>
</web-app>
```

#### ServletContext
`ServletConfig`의 초기값은 지정된 Servlet에서만 사용이 가능하나, `ServletContext`는 모든 Application이 공용으로 사용하는 초기값을 설정</br>
값은 `getServletContext().getInitParameter("저장명")`으로 호출</br>
`<servlet>` 태그 내부가 아닌 `<web-app>` 내부에 설정

```xml
<web-app>
    <context-param>
        <param-name>저장명</param-name>
        <param-value>설정값</param-value>
    </context-param>
</web-app>
```

> ### Context Path
Application에 접근하는 경로로, 컨테이너에서 Application을 구분하는 root 경로</br>
프로젝트의 별칭은 Tomcat 서버 설정의 `server.xml` 파일 내 `<Context>` 설정을 따름

```plaintext
http://localhost:[PORT번호]/[프로젝트 별칭]/[Servlet 명]
예시: http://localhost:8800/first/test1.do
```

> ### Servlet의 LifeCycle과 구동
Servlet의 LifeCycle은 다음과 같음
1. 첫 요청이면, 객체를 생성하며 `init()` 메서드를 호출
2. 이후 작업이 실행될 때마다 `service()` 메서드가 요청한 HTTP 타입에 따라 `doGet()`, `doPost()` 메서드를 호출
3. 최종적으로 Servlet이 서비스 되지 않을 때 `destroy()` 메서드가 호출됨

Servlet의 주요 메서드는 Servlet의 LifeCycle과 유사

[뒤로](ServletJSP.md)
