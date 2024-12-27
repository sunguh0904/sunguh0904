## Configuration 클래스
> ### Configuration 클래스란?
Configuration 클래스는 MyBatis에서 설정 정보를 관리하는 데 사용되는 클래스</br>
주로 매퍼, 환경 설정, 플러그인, 타입 핸들러 등을 포함한 설정을 관리함

> ### Configuration 클래스의 주요 기능
1. 매퍼 설정: 매퍼 파일이나 클래스의 위치를 설정
    ```java
    Configuration configuration = new Configuration();
    configuration.addMapper(MyMapper.class);
    ```

2. 환경 설정: 환경 정보를 설정
    ```java
    Environment environment = new Environment("development", transactionFactory, dataSource);
    configuration.setEnvironment(environment);
    ```

3. 플러그인 설정: MyBatis 플러그인을 설정
    ```java
    configuration.addInterceptor(new MyPlugin());
    ```

4. 타입 핸들러 설정: 사용자 정의 타입 핸들러를 설정
    ```java
    configuration.getTypeHandlerRegistry().register(MyTypeHandler.class);
    ```

> ### 왜 사용해야 하는가?
1. **중앙 집중식 설정 관리**: MyBatis 설정을 중앙에서 관리할 수 있음
2. **유연성**: 다양한 설정을 통해 MyBatis의 동작을 커스터마이징할 수 있음
3. **확장성**: 플러그인과 타입 핸들러를 통해 MyBatis의 기능을 확장할 수 있음

> ### 쉬운 요약
1. Configuration 클래스는 MyBatis 설정을 관리하는 클래스
    - 주로 매퍼, 환경 설정, 플러그인, 타입 핸들러 등을 포함한 설정을 관리함

2. 매퍼 설정, 환경 설정, 플러그인 설정, 타입 핸들러 설정 기능을 제공

> ### 비유
1. 설정 관리자
    - Configuration 클래스는 MyBatis 설정을 중앙에서 관리하는 관리자와 같음
    - 예: 매퍼 파일, 환경 정보, 플러그인, 타입 핸들러 등을 설정

2. 환경 설정 파일
    - Configuration 클래스는 MyBatis의 환경 설정 파일과 같음
    - 예: 매퍼 파일, 환경 정보, 플러그인, 타입 핸들러 등을 설정

[뒤로](MyBatis.md)
