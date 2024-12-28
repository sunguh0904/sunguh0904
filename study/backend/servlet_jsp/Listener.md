## Servlet Listener
> ### Servlet Listener 개요
Servlet Listener는 웹 컨테이너가 관리하는 LifeCycle 사이에 발생하는 이벤트를 감지하여, 이벤트 발생 시 그에 대한 일련의 로직을 처리하는 인터페이스

#### Servlet Listener 사용하는 경우
1. Web context가 초기화되는 경우
2. Session이 생성되거나 소멸되는 경우
3. 요청 정보의 속성이 바뀌는 경우

> ### Servlet Listener 종류
#### ServletContextListener
웹 애플리케이션의 시작과 종료 시 자동 발생하는 이벤트로, Context 생성/소멸 및 Application 생성/소멸 시점에 로직을 처리

```java
public class MyServletContextListener implements ServletContextListener {
    @Override
    public void contextInitialized(ServletContextEvent e) {
        // 웹 컨테이너가 처음 구동되어 ServletContext가 생성될 때 작동
    }

    @Override
    public void contextDestroyed(ServletContextEvent e) {
        // 웹 컨테이너가 종료될 때, ServletContext가 소멸될 때 작동
    }
}
```

#### ServletContextAttributeListener
웹 컨테이너에 저장된 속성의 값이 변경될 경우 발생하는 이벤트로, ServletContext 객체에 속성이 추가, 삭제, 수정되는 시점에 로직을 처리

```java
public class MyServletContextAttributeListener implements ServletContextAttributeListener {
    @Override
    public void attributeAdded(ServletContextAttributeEvent e) {
        // 새로운 속성 값이 추가될 때 실행
    }

    @Override
    public void attributeRemoved(ServletContextAttributeEvent e) {
        // 속성 값이 제거될 때 실행
    }

    @Override
    public void attributeReplaced(ServletContextAttributeEvent e) {
        // 속성 값이 변경될 때 실행
    }
}
```

#### HttpSessionListener
HTTP session의 생성 및 소멸 시에 작동하는 이벤트로, HttpSession 객체가 생성되거나 소멸되는 시점에 로직을 처리

```java
public class MyHttpSessionListener implements HttpSessionListener {
    @Override
    public void sessionCreated(HttpSessionEvent e) {
        // Session 생성 시 실행
    }

    @Override
    public void sessionDestroyed(HttpSessionEvent e) {
        // Session 무효화 될 때 실행
    }
}
```

#### HttpSessionAttributeListener
HTTP Session에 대한 속성의 값이 변경될 경우 발생하는 이벤트로, HttpSession에 대한 속성 값이 변경될 경우 로직을 처리

```java
public class MyHttpSessionAttributeListener implements HttpSessionAttributeListener {
    @Override
    public void attributeAdded(HttpSessionBindingEvent e) {
        // Session에 새로운 속성 값이 추가될 때 실행
    }

    @Override
    public void attributeRemoved(HttpSessionBindingEvent e) {
        // Session에 속성 값이 제거될 때 실행
    }

    @Override
    public void attributeReplaced(HttpSessionBindingEvent e) {
        // Session에 속성 값이 변경될 때 실행
    }
}
```

#### HttpSessionActivationListener
HTTP Session이 활성화 또는 비활성화를 감지했을 때 작동하며, HttpSession이 새로 생성되어 활성화될 때 로직을 처리

```java
public class MyHttpSessionActivationListener implements HttpSessionActivationListener {
    @Override
    public void sessionDidActivate(HttpSessionEvent e) {
        // Session 활성화 될 때
    }

    @Override
    public void sessionWillPassivate(HttpSessionEvent e) {
        // Session 비활성화 되려고 할 때
    }
}
```

#### HttpSessionBindingListener
현재 Session에 객체가 추가되거나 해제될 때 발생하는 이벤트로, 사용자의 현재 Session에 바인딩 되거나 해제될 객체가 발생할 경우 로직을 수행

```java
public class MyHttpSessionBindingListener implements HttpSessionBindingListener {
    @Override
    public void valueBound(HttpSessionBindingEvent e) {
        // 객체가 Session에 연결될 때 실행
    }

    @Override
    public void valueUnbound(HttpSessionBindingEvent e) {
        // 객체가 Session으로부터 연결이 해제될 때 실행
    }
}
```

[뒤로](ServletJSP.md)
