## SqlSessionFactory와 SqlSessionFactoryBuilder 클래스
> ### SqlSessionFactory 클래스란?
SqlSessionFactory 클래스는 MyBatis에서 SQL 세션을 생성하고 관리하는 데 사용되는 클래스</br>
주로 데이터베이스와의 상호작용을 위한 SqlSession 객체를 생성함

> ### SqlSessionFactoryBuilder 클래스란?
SqlSessionFactoryBuilder 클래스는 SqlSessionFactory 객체를 생성하는 데 사용되는 클래스</br>
주로 설정 파일이나 설정 객체를 기반으로 SqlSessionFactory를 생성함

> ### 주요 기능
1. SqlSessionFactory 생성: SqlSessionFactoryBuilder를 사용하여 SqlSessionFactory 객체를 생성
    ```java
    SqlSessionFactory sqlSessionFactory = new SqlSessionFactoryBuilder().build(inputStream);
    ```

2. SqlSession 생성: SqlSessionFactory를 사용하여 SqlSession 객체를 생성
    ```java
    try (SqlSession session = sqlSessionFactory.openSession()) {
        // 데이터베이스 작업 수행
    }
    ```

3. 환경 설정: SqlSessionFactoryBuilder를 사용하여 환경 설정을 적용
    ```java
    SqlSessionFactory sqlSessionFactory = new SqlSessionFactoryBuilder().build(configuration);
    ```

4. 트랜잭션 관리: SqlSession 객체를 통해 트랜잭션을 관리
    ```java
    try (SqlSession session = sqlSessionFactory.openSession()) {
        session.commit();
    }
    ```

> ### 왜 사용해야 하는가?
1. **중앙 집중식 세션 관리**: SqlSessionFactory를 통해 SQL 세션을 중앙에서 관리할 수 있음
2. **유연성**: 다양한 설정을 통해 SqlSession 객체의 동작을 커스터마이징할 수 있음
3. **트랜잭션 관리**: SqlSession 객체를 통해 트랜잭션을 쉽게 관리할 수 있음

> ### 쉬운 요약
1. SqlSessionFactory 클래스는 MyBatis에서 SQL 세션을 생성하고 관리하는 클래스
    - 주로 데이터베이스와의 상호작용을 위한 SqlSession 객체를 생성함

2. SqlSessionFactoryBuilder 클래스는 SqlSessionFactory 객체를 생성하는 클래스
    - 주로 설정 파일이나 설정 객체를 기반으로 SqlSessionFactory를 생성함

> ### 비유
1. 세션 관리자
    - SqlSessionFactory 클래스는 MyBatis에서 SQL 세션을 중앙에서 관리하는 관리자와 같음
    - 예: SqlSession 객체를 생성하고 트랜잭션을 관리

2. 세션 팩토리 빌더
    - SqlSessionFactoryBuilder 클래스는 MyBatis의 세션 팩토리 빌더와 같음
    - 예: 설정 파일이나 설정 객체를 기반으로 SqlSessionFactory를 생성

[뒤로](MyBatis.md)
