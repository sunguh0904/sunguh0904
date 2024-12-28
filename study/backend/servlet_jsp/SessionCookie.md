## Session & Cookie
> ### Session & Cookie 개요
HTTP 통신은 서버와 클라이언트 간의 요청과 응답으로 데이터를 주고 받는 형식</br>
서버는 클라이언트의 요청에 응답하면 연결을 끊음 (stateless)</br>
따라서 클라이언트는 서버에 또 다른 요청을 하려면 새로 연결하여 응답을 받아야 함

#### HTTP 통신의 특징
1. 무 연결
    - 클라이언트가 서버로 요청할 때, 요청과 응답이 존재하는데 계속 연결된 상태가 아님
    - HTTP는 요청할 때 잠깐, 응답할 때 잠깐만 연결하는, 무 연결의 특징을 가짐
    - 기본적으로 HTTP는 TCP 프로토콜(=연결지향 프로토콜: 요청 시 수락해야 송수신 가능함)에 특화 기능을 추가하여 사용

2. 무 상태
    - 서블릿 컨테이너 내 여러 개의 서블릿이 있는데, 각각의 서블릿에서 상태값(속성, 변수값)을 다른 서블릿에서 공유해 쓸 수 없음을 의미

#### 문제점
유지되어야 하는 정보가 연결이 끊어지면서 사라지는 문제가 발생</br>
(예시: 로그인 후의 로그인 계정 정보, 장바구니에 넣은 데이터 등)

> ### Session과 Cookie로 해결
연결이 끊어진 후에도 클라이언트에 대한 정보를 유지하기 위한 두 가지 방법이 있음</br>
두 가지 방법이 바로 서버 측에 데이터를 보관하는 Session과 클라이언트 측에 데이터를 보관하는 Cookie

> ### Cookie
#### Cookie란
클라이언트 측, 즉 사용자 컴퓨터에 데이터를 저장하는 기술로, 필요 시에 저장한 정보를 서버와 공유하여 정보를 유지</br>
데이터는 Map 형식으로 저장되고, 데이터의 크기, 개수에 제한이 있음</br>
Cookie 유지 시간, 유효 디렉토리, 유효 도메인 등을 설정할 수 있음</br>
Cookie는 간단하게 이용할 수 있다는 장점이 있으나, 공용 PC를 사용하거나 URL에 일부 데이터를 포함하는 경우 보안에 취약</br>
패키지: `javax.servlet.http.Cookie`

#### Cookie 속성 설정
- `name=value`: ASCII 문자만 사용 가능하며, 한번 설정된 쿠키의 name은 수정할 수 없음
- `expire='날짜'`: Cookie의 유지 시간으로, 설정이 따로 없으면 브라우저 동작 동안 유지
- `path='경로'`: Cookie가 전달되는 서버의 유효 디렉토리를 지정하는 속성
- `domain='서버정보'`: Cookie가 전달되는 유효 서버를 설정
- `secure`: HTTPS나 SSL 보안 프로토콜로 요청할 때만 서버에 전송

#### Cookie 설정 및 전송
1. Cookie Class를 생성 (패키지 import)
    ```java
    Cookie cookie = new Cookie("name", "value");
    ```

2. 생성된 Cookie의 설정값을 지정
    ```java
    cookie.setMaxAge(60 * 60); // 유효 시간 설정 (1시간)
    cookie.setPath("/"); // 경로 설정
    cookie.setDomain("example.com"); // 도메인 설정
    ```

3. 생성된 Cookie를 전송
    ```java
    response.addCookie(cookie); // 생성된 쿠키 전송
    ```

#### 전송한 Cookie 활용
1. 클라이언트에서 전송한 Cookie를 `HttpServletRequest` 객체를 이용해 읽어옴
    ```java
    Cookie[] cookies = request.getCookies();
    ```

2. Cookie 값을 호출
    ```java
    for (Cookie cookie : cookies) {
        System.out.println(cookie.getName() + " " + cookie.getValue());
    }
    ```

#### Cookie 확인 방법
- Explorer: 개발자 도구(F12) → Network → 페이지 선택 → 우측 화면 Cookie
- Chrome: 개발자 도구(F12) → Application → Cookies에서 확인

> ### Session
#### Session이란
서버에 데이터를 저장하는 기술로, 클라이언트에는 Session ID를 부여하고 클라이언트가 request로 Session ID를 보내면 ID가 일치하는 Session 정보를 컨테이너가 생성하여 그 객체의 데이터를 사용</br>
서버에서 관리하므로 보안상 안전하고, 브라우저가 종료되면 Session도 소멸</br>
패키지: `javax.servlet.http.HttpSession`

#### 데이터 상태 저장 영역
1. Page scope: 하나의 Servlet, 하나의 Class에서만 공유 가능
2. Request scope: forward에 한정해 공유할 수 있는 범위
3. Session scope: redirect 방식에서도 활용할 수 있는 범위로 대표적으로 로그인 정보가 이 영역에 속함
4. Application scope: 브라우저별 정보보다 넓은 범위

#### Session 생성
Session 객체를 컨테이너가 자동으로 생성하여 request 객체에 넣어주므로, 해당 객체를 불러오는 것을 생성이라고 함

```java
HttpSession session = request.getSession();
```

#### Session 설정 및 호출
1. 생성된 Session의 값을 설정
    ```java
    session.setAttribute("name", "value"); // Session 데이터 설정
    session.setMaxInactiveInterval(30 * 60); // Session 유지시간 설정 (30분)
    ```

2. 생성된 Session을 호출
    ```java
    HttpSession session = request.getSession();
    String value = (String) session.getAttribute("name"); // 데이터 불러옴
    ```

#### Session Method
| method명 | 내용 |
|----------|------|
| setAttribute(String, Object) | request 객체에 전달하고 싶은 값을 String 이름-Object 값으로 설정 |
| getAttribute(String) | 매개변수와 동일한 객체의 속성 값 가져옴 |
| getAttributeNames() | 객체에 등록되어 있는 모든 속성의 이름만 반환 |
| removeAttribute(String) | request 객체에 저장된 매개변수와 동일한 속성 값 삭제 |
| getId() | Session ID 값 가져옴 |
| getCreationTime() | Session 객체가 생성된 시간 반환 (msec) |
| getMaxInactiveInterval() | 클라이언트 요청이 없을 때, 서버가 현재 Session을 언제까지 유지할지 초 단위로 반환 (default = 30분) |
| getLastAccessedTime() | 클라이언트 요청이 마지막으로 시도된 시간 반환 (msec) |
| isNew() | 새로 생성된 Session이면 true, 아니면 false 반환 |
| invalidate() | 현재 Session 삭제 |
| setMaxInactiveInterval(int) | 객체 유지 시간을 설정하고, 지정 시간 지나면 객체 자동 삭제 |

[뒤로](ServletJSP.md)
