## JDBC Connection Class
> ### Connection 클래스란?
Connection 클래스는 JDBC에서 데이터베이스와의 연결을 나타내는 클래스입니다. 이 클래스는 데이터베이스와의 연결을 설정하고, SQL 문을 실행할 수 있는 객체를 생성하는 데 사용됩니다.

> ### Connection 클래스의 주요 기능
1. 데이터베이스 연결 설정: 데이터베이스 URL, 사용자 이름, 비밀번호를 사용하여 연결을 설정합니다.
    ```java
    // DriverManager를 사용하여 데이터베이스에 연결
    Connection connection = DriverManager.getConnection(url, user, password);
    ```

2. SQL 문 실행 객체 생성: SQL 문을 실행할 수 있는 Statement, PreparedStatement, CallableStatement 객체를 생성합니다.
    ```java
    // 일반 SQL 문을 실행하기 위한 Statement 객체 생성
    Statement statement = connection.createStatement();
    
    // 파라미터가 포함된 SQL 문을 실행하기 위한 PreparedStatement 객체 생성
    PreparedStatement preparedStatement = connection.prepareStatement("SELECT * FROM employees WHERE id = ?");
    
    // 저장 프로시저를 호출하기 위한 CallableStatement 객체 생성
    CallableStatement callableStatement = connection.prepareCall("{call getEmployee(?)}");
    ```

3. 트랜잭션 관리: 자동 커밋 모드를 설정하고, 트랜잭션을 커밋하거나 롤백할 수 있습니다.
    ```java
    // 자동 커밋 모드를 비활성화하여 수동으로 트랜잭션을 관리
    connection.setAutoCommit(false);
    
    // 트랜잭션을 커밋하여 변경 사항을 데이터베이스에 반영
    connection.commit();
    
    // 트랜잭션을 롤백하여 변경 사항을 취소
    connection.rollback();
    ```

4. 연결 종료: 데이터베이스와의 연결을 종료합니다.
    ```java
    // 데이터베이스와의 연결을 종료하여 자원을 해제
    connection.close();
    ```

> ### 왜 사용해야 하는가?
1. **데이터베이스 연동**: Connection 클래스를 사용하면 자바 애플리케이션에서 데이터베이스와의 연결을 설정하고 SQL 문을 실행할 수 있음
2. **트랜잭션 관리**: 트랜잭션을 관리하여 데이터베이스 작업의 일관성을 유지할 수 있음
3. **자원 관리**: 사용이 끝난 후 연결을 종료하여 자원을 효율적으로 관리할 수 있음

> ### 쉬운 요약
1. Connection 클래스는 "데이터베이스와의 연결을 나타내는 클래스"
    - 데이터베이스 연결 설정, SQL 문 실행 객체 생성, 트랜잭션 관리, 연결 종료 기능을 제공

> ### 비유
1. 전화 연결
    - Connection 클래스는 전화 연결에서 "전화선을 연결하고 통화하는 과정"과 같음
    - 예: 전화선을 연결하고, 통화하고, 통화가 끝나면 전화선을 끊는 과정

2. 은행 계좌
    - Connection 클래스는 은행 계좌에서 "계좌를 개설하고, 거래를 수행하고, 계좌를 닫는 과정"과 같음
    - 예: 계좌를 개설하고, 돈을 입금하거나 출금하고, 계좌를 닫는 과정

[뒤로](JDBC.md)
