## SqlSession 클래스
> ### SqlSession 클래스란?
SqlSession 클래스는 MyBatis에서 SQL 쿼리를 실행하고 데이터베이스와 상호작용하는 데 사용되는 클래스</br>
주로 데이터베이스 작업(삽입, 업데이트, 삭제, 조회)을 수행함

> ### SqlSession 클래스의 주요 기능
1. 데이터 조회: SQL 쿼리를 실행하여 데이터를 조회
    ```java
    try (SqlSession session = sqlSessionFactory.openSession()) {
        List<Employee> employees = session.selectList("selectEmployees");
    }
    ```

2. 데이터 삽입: SQL 쿼리를 실행하여 데이터를 삽입
    ```java
    try (SqlSession session = sqlSessionFactory.openSession()) {
        session.insert("insertEmployee", employee);
        session.commit();
    }
    ```

3. 데이터 업데이트: SQL 쿼리를 실행하여 데이터를 업데이트
    ```java
    try (SqlSession session = sqlSessionFactory.openSession()) {
        session.update("updateEmployee", employee);
        session.commit();
    }
    ```

4. 데이터 삭제: SQL 쿼리를 실행하여 데이터를 삭제
    ```java
    try (SqlSession session = sqlSessionFactory.openSession()) {
        session.delete("deleteEmployee", employeeId);
        session.commit();
    }
    ```

5. 트랜잭션 관리: 트랜잭션을 시작, 커밋, 롤백
    ```java
    try (SqlSession session = sqlSessionFactory.openSession()) {
        session.commit();
        session.rollback();
    }
    ```

> ### 왜 사용해야 하는가?
1. **데이터베이스 작업 수행**: SqlSession을 사용하여 데이터베이스 작업을 쉽게 수행할 수 있음
2. **트랜잭션 관리**: SqlSession을 통해 트랜잭션을 쉽게 관리할 수 있음
3. **유연성**: 다양한 SQL 쿼리를 실행하여 데이터베이스와 상호작용할 수 있음

> ### 쉬운 요약
1. SqlSession 클래스는 MyBatis에서 SQL 쿼리를 실행하고 데이터베이스와 상호작용하는 클래스
    - 주로 데이터베이스 작업(삽입, 업데이트, 삭제, 조회)을 수행함

2. 데이터 조회, 삽입, 업데이트, 삭제, 트랜잭션 관리 기능을 제공

> ### 비유
1. 데이터베이스 작업자
    - SqlSession 클래스는 MyBatis에서 SQL 쿼리를 실행하고 데이터베이스 작업을 수행하는 작업자와 같음
    - 예: 데이터를 조회, 삽입, 업데이트, 삭제

2. 트랜잭션 관리자
    - SqlSession 클래스는 MyBatis에서 트랜잭션을 관리하는 관리자와 같음
    - 예: 트랜잭션을 시작, 커밋, 롤백

[뒤로](MyBatis.md)
