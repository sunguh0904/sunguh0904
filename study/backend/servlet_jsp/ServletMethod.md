## Servlet Method
> ### 데이터 전송 방식에 따른 Method
사용자 데이터 전송 방식에는 get 방식과 post 방식이 있음

#### get 방식
- URL창에 "?" 뒤에 데이터를 입력하는 방법(= 쿼리스트링)으로 전송
- 전송 데이터가 여러 개이면 &로 묶어서 보냄
- 데이터 검색에 주로 사용되며, 데이터 크기 한계가 있고 보안에 취약

#### post 방식
- HTTP header의 내용으로 데이터를 전송
- 전송 데이터 크기에 제한이 없고, header에 포함해 전송하므로 보안이 뛰어남

> ### 데이터 전송 방식에 따른 Servlet Method
Servlet이 get, post의 두 방식 중 하나로 전달 받으면 해당하는 method를 호출</br>
html에서 method 속성을 이용해 방식을 결정하며, default는 get 방식

1. `doGet`: client에서 데이터 전송 방식을 get으로 전송하면 호출되는 method
2. `doPost`: client에서 데이터 전송 방식을 post로 전송하면 호출되는 method

```java
// doGet 메서드 예제
protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
    // 처리 로직
}

// doPost 메서드 예제
protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
    // 처리 로직
}
```

> ### Servlet 매개변수 객체
Servlet 매개변수 객체에는 `HttpServletRequest`와 `HttpServletResponse`가 있음

#### HttpServletRequest (interface)
HTTP Servlet을 위한 요청 정보(request information)를 제공하는 method를 지정

```java
// getParameter 메서드 예제
String value = request.getParameter("paramName");

// setAttribute 메서드 예제
request.setAttribute("attrName", attrValue);

// getRequestDispatcher 메서드 예제
RequestDispatcher dispatcher = request.getRequestDispatcher("path/to/resource");
dispatcher.forward(request, response);
```

#### HttpServletResponse (interface)
요청에 대한 처리 결과를 작성하기 위해 사용하는 객체

```java
// setContentType 메서드 예제
response.setContentType("text/html");

// getWriter 메서드 예제
PrintWriter out = response.getWriter();
out.println("Response content");

// sendRedirect 메서드 예제
response.sendRedirect("newPage.jsp");
```

> ### sendRedirect & RequestDispatcher
#### sendRedirect & encodeRedirectURL
client 브라우저에게 "(매개변수로 등록한) 페이지를 재요청하라"고 응답</br>
`encodeRedirectURL`은 매개변수(URL)에 Session ID 정보를 추가하여 재요청 처리

```java
// sendRedirect 메서드 예제
response.sendRedirect("newPage.jsp");

// encodeRedirectURL 메서드 예제
String url = response.encodeRedirectURL("newPage.jsp");
response.sendRedirect(url);
```

#### RequestDispatcher() ~ forward()
컨테이너 내에서 처음 요청 받은 페이지가 요청 데이터 (`HttpServletRequest`, `HttpServletResponse`)를 다른 페이지에 전송하여 처리를 요청하고, 자신이 처리한 것처럼 응답</br>
따라서 url 주소(페이지)가 변경되지 않음

```java
// RequestDispatcher와 forward 메서드 예제
RequestDispatcher dispatcher = request.getRequestDispatcher("newPage.jsp");
dispatcher.forward(request, response);
```

> ### 객체별 공유 데이터 설정
공유 데이터는 Map 형식으로 저장됨</br>
`ServletContext`, `ServletRequest`, `HttpSession` 객체에서 사용하는 method는 다음과 같음

```java
// setAttribute 메서드 예제
request.setAttribute("attrName", attrValue);

// getAttribute 메서드 예제
Object value = request.getAttribute("attrName");

// removeAttribute 메서드 예제
request.removeAttribute("attrName");
```

[뒤로](ServletJSP.md)
