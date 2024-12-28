## Servlet Filter & Wrapper
> ### Servlet Filter 개요
Servlet Filter는 `javax.servlet.Filter` 인터페이스를 상속 받아 구현하는 클래스</br>
HTTP 요청과 응답 사이에서 전달되는 데이터를 가로채어, 서비스에 맞게 변경하고 걸러내는 필터링 작업을 수행</br>
필터 설정에 따라 해당하는 요청 및 응답 시에 반드시 거쳐야 하며, 비밀번호 암호화 처리, 인코딩 설정 등 공통 관리에 해당하는 기능을 수행할 수 있음

#### Servlet Filter 처리 내용
- Request에 대한 처리
  - 보안 관련 사항
  - 요청 header와 body 형식 지정
  - 요청에 대한 log 기록 유지
- Response에 대한 처리
  - 응답 stream 압축
  - 응답 stream 내용 추가 및 수정
  - 새로운 응답 작성

#### Filter Chain (Interface)
여러 개의 Filter를 연결하여 사용할 수 있음</br>
`doFilter()` 메서드를 이용하여 순차적으로 실행

```java
// doFilter 메서드 예제
public void doFilter(ServletRequest req, ServletResponse res, FilterChain chain) throws IOException, ServletException {
    // 필터링 작업
    chain.doFilter(req, res); // 다음 필터 실행
}
```

> ### Servlet Filter 사용
#### DD 설정 (= web.xml 설정)
Filter를 등록하고, url 패턴과 Filter를 매핑

```xml
<filter>
    <filter-name>Filter 설정명</filter-name>
    <filter-class>Filter 구현 Class명</filter-class>
    <init-param>
        <param-name>초기값 설정명</param-name>
        <param-value>초기 설정값</param-value>
    </init-param>
</filter>

<filter-mapping>
    <filter-name>등록된 Filter명</filter-name>
    <url-pattern>요청할 페이지 형식</url-pattern>
</filter-mapping>
```

#### Filter Interface
```java
public class Class명 implements Filter {
    @Override
    public void init(FilterConfig config) throws ServletException {
        // Filter 호출 시 작업 설정
    }

    @Override
    public void doFilter(ServletRequest req, ServletResponse res, FilterChain chain) throws IOException, ServletException {
        // Filtering 작업할 내용
        chain.doFilter(req, res); // 다음 필터 실행
    }

    @Override
    public void destroy() {
        // 삭제 시 작업 설정
    }
}
```

#### 예시
1. `CharsetEncodingFilter` 클래스를 작성
2. 작성한 Filter를 `web.xml`에 등록

> ### Servlet Wrapper
#### Servlet Wrapper란
관련 클래스(`ServletRequest`, `ServletResponse`, `HttpServletRequest`, `HttpServletResponse`)를 내부에 보관하며 그 인터페이스를 구현한 객체를 참조하여 구현 메서드를 위임</br>
사용자가 별도의 request나 response 객체를 생성하여 활용할 때 Wrapper 클래스를 상속하여 활용하면, 원하는 클래스만 재정의하여 사용 가능

#### Wrapper Class
- `HttpServletRequestWrapper`: 요청한 정보를 변경하는 Wrapper 클래스
    ```java
    public class SampleWrapper extends HttpServletRequestWrapper {
        public SampleWrapper(HttpServletRequest request) {
            super(request);
        }
        // 추가적인 메서드 재정의
    }
    ```

- `HttpServletResponseWrapper`: 응답할 정보를 변경하는 Wrapper 클래스
    ```java
    public class SampleWrapper extends HttpServletResponseWrapper {
        public SampleWrapper(HttpServletResponse response) {
            super(response);
        }
        // 추가적인 메서드 재정의
    }
    ```

[뒤로](ServletJSP.md)
