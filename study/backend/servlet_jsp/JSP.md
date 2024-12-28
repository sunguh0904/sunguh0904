## JSP (Java Server Page)
> ### JSP 개요
JSP(Java Server Page)는 자바 기반의 웹 애플리케이션을 개발하기 위한 기술</br>
HTML 코드에 자바 코드를 삽입하여 동적인 웹 페이지를 생성

#### Servlet과 JSP 비교
| Servlet | JSP |
|---------|-----|
| Java 코드에 HTML 코드를 삽입 | HTML 코드에 Java 코드를 삽입 |
| Business 로직 처리에 적합 | 화면 로직 처리에 적합 |
| `out.println("<HTML>");` | `<% for (int i=0; i<10; i++) { %>` |

기존 Servlet은 서버 측에서 자바 문법을 활용해 동적 페이지를 만들어서 응답</br>
이 방식이 불편한 이유는 크게 두 가지:
1. HTML 태그가 아니라 문자열 형태로 작성해야 함 (편집기 사용 불가)
2. Servlet은 작은 부분이라도 수정하면 서버(Tomcat)를 재시작해서 컴파일해야 함

따라서 JSP 기술의 목표는 Servlet의 Business 로직으로부터 화면 로직을 분리하는 것

> ### JSP 실행 방식
Client에서 사용하는 HTML 문서를 베이스로 하며, HTML 문서 내에 작성하면 Servlet에서 문자열을 통해 생성하는 코드로 변환하여 사용자에게 동적인 페이지를 편리하게 내보내는 방식

> ### JSP 특징
1. JSP 파일이 변경되지 않는다면 `.jsp` 파일에 대한 컴파일은 다시 일어나지 않음
2. JSP 파일이 변경될 때마다 Web Container는 translation, compile, load, initialization 과정을 수행
    - 주의: 구 버전의 JSP 파일을 overwrite 할 경우 제대로 반영되지 않는 경우가 발생할 수 있음
3. JSP 파일의 배포 환경(위치)은 HTML과 동일 (WEB_ROOT 폴더 하단)

[뒤로](ServletJSP.md)
