## JSP 내장 객체
> ### JSP 내장 객체란?
JSP에서 기본적으로 제공하는 객체로 `request`, `response`, `out` 등 Scriptlet tag와 Expression tag에서 사용할 수 있도록 암시적으로 선언된 객체

> ### JSP 내장 객체의 종류
| 내장 객체명 | 설명 |
|-------------|------|
| request | HttpServletRequest 객체 참조 변수 |
| response | HttpServletResponse 객체 참조 변수 |
| out | JspWriter 객체 참조 변수 |
| session | HttpSession 객체 참조 변수 |
| application | ServletContext 객체 참조 변수 |
| page | 현재 JSP 페이지에 대한 참조 변수 |
| exception | 발생하는 Throwable 객체에 대한 참조 변수 |

> ### JSP 내장 객체의 영역
| 영역 | 설명 |
|------|------|
| page | 하나의 JSP를 처리할 때 사용되는 영역 |
| request | 하나의 요청을 처리할 때 사용되는 영역 |
| session | 하나의 브라우저와 관련된 영역 |
| application | 하나의 웹 Application과 관련된 영역 |

> ### 내장 객체의 주요 method
#### Request
| method명 | 설명 |
|----------|------|
| getParameter(name) | name 파라미터의 값을 반환 |
| getParameterValues(name) | name 파라미터의 값을 배열 형태로 반환 |
| getParameterNames() | 요청에 포함된 파라미터명을 모두 반환 |
| getMethod() | 현재 요청 방식 반환 (GET, POST) |
| getSession() | 현재 Session 객체 반환 |
| setCharacterEncoding() | client에서 서버로 전달된 값을 지정한 문자셋으로 변경 |

#### Response
| method명 | 설명 |
|----------|------|
| sendRedirect(url) | 응답 결과를 요청으로 하여 지정된 url에 재전송 |
| setStatus(int status_code) | 응답으로 전송될 상태 코드를 설정 (성공일 경우 기본값은 ‘200’, OK임) |
| sendError(int status_code) | 에러가 발생하면 응답 header에 상태 코드 설정 |
| setContentType(String) | 서버에서 client로 전달될 값의 데이터 타입 설정 |

> ### HTTP Request 전송의 GET 방식과 POST 방식
HTTP 프로토콜을 통해 데이터를 전송할 때 보통 GET, POST 이 두 가지의 Request Method를 사용

#### GET 방식
- 요청한 정보와 함께 전달되는 파라미터 값이 URL 내부에 쿼리 스트링(query string)으로 저장되어 보내짐

#### POST 방식
- 서버로 전달하는 파라미터 값이 HTTP 메시지 body 안에 저장되어 보내짐

#### Query String이란?
사용자가 서버로 데이터를 전달할 때, 전송된 데이터들을 URL의 뒷부분에 `?`로 구분지어 전송하는 것</br>
`key`는 input 태그의 name 값을, `value`는 input 태그의 value 값을 뜻함</br>
`?`는 Query String의 시작을 의미하며, `&`는 각 데이터 간의 구분자를 뜻함

[뒤로](JSP.md)
