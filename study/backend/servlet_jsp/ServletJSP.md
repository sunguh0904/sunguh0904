# Servlet & JSP Study Notes
> ### Servlet & JSP란?
Servlet과 JSP는 자바 기반의 웹 애플리케이션을 개발하기 위한 기술</br>
Servlet은 자바 코드로 작성된 서버 측 프로그램이고, JSP는 HTML 내에 자바 코드를 삽입하여 동적인 웹 페이지를 생성하는 기술

> ### Servlet & JSP의 주요 기능
1. 동적 웹 페이지 생성: 사용자의 요청에 따라 동적으로 웹 페이지를 생성
    ```java
    // Servlet 예제
    @WebServlet("/hello")
    public class HelloServlet extends HttpServlet {
        protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
            response.setContentType("text/html");
            PrintWriter out = response.getWriter();
            out.println("<h1>Hello, Servlet!</h1>");
        }
    }
    ```

    ```jsp
    <!-- JSP 예제 -->
    <html>
    <body>
        <h1>Hello, JSP!</h1>
        <%
            String name = request.getParameter("name");
            out.println("<p>Welcome, " + name + "!</p>");
        %>
    </body>
    </html>
    ```

2. 요청 및 응답 처리: 클라이언트의 요청을 처리하고, 서버의 응답을 생성
    ```java
    // Servlet 예제
    @WebServlet("/login")
    public class LoginServlet extends HttpServlet {
        protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
            String username = request.getParameter("username");
            String password = request.getParameter("password");
            // 로그인 처리 로직
        }
    }
    ```

    ```jsp
    <!-- JSP 예제 -->
    <html>
    <body>
        <form action="login" method="post">
            <label for="username">Username:</label>
            <input type="text" id="username" name="username">
            <label for="password">Password:</label>
            <input type="password" id="password" name="password">
            <button type="submit">Login</button>
        </form>
    </body>
    </html>
    ```

> ### 왜 사용해야 하는가?
1. **동적 웹 페이지 생성**: Servlet과 JSP를 사용하면 사용자의 요청에 따라 동적으로 웹 페이지를 생성할 수 있음
2. **요청 및 응답 처리**: 클라이언트의 요청을 처리하고, 서버의 응답을 생성할 수 있음
3. **자바 기반**: 자바 언어의 장점을 활용하여 안정적이고 확장 가능한 웹 애플리케이션을 개발할 수 있음

> ### 쉬운 요약
1. Servlet과 JSP는 "자바 기반의 웹 애플리케이션을 개발하기 위한 기술"
    - Servlet은 자바 코드로 작성된 서버 측 프로그램이고, JSP는 HTML 내에 자바 코드를 삽입하여 동적인 웹 페이지를 생성

2. 동적 웹 페이지 생성, 요청 및 응답 처리 기능을 제공

> ### 비유
1. 요리사와 레시피
    - Servlet은 "요리사"와 같고, JSP는 "요리 레시피"와 같음
    - 예: 요리사가 레시피를 보고 요리를 준비하고, 요리를 완성하는 과정

2. 주문 처리 시스템
    - Servlet과 JSP는 "주문 처리 시스템"과 같음
    - 예: 고객의 주문을 받고, 주문에 따라 요리를 준비하고, 요리를 제공하는 과정

## 추가 자료
1. [Servlet & JSP 개요: Servlet과 JSP의 개요](Overview.md)
2. [Servlet LifeCycle: Servlet의 생명 주기와 구동](ServletLifecycle.md)
3. [Servlet Method: 데이터 전송 방식에 따른 Servlet 메서드](ServletMethod.md)
4. [Session & Cookie: 세션과 쿠키 이해하기](SessionCookie.md)
5. [Filter & Wrapper: 필터와 래퍼 이해하기](FilterWrapper.md)

[뒤로](/README.md)
