# JDBC Study Notes
> ### JDBC 란?
JDBC(Java Database Connectivity)는 자바에서 데이터베이스에 접속하고 SQL 쿼리를 실행하기 위한 API

> ### JDBC의 주요 구성 요소
1. DriverManager: 데이터베이스 드라이버를 관리하고 연결을 설정
    ```java
    Connection connection = DriverManager.getConnection(url, user, password);
    ```

2. Connection: 데이터베이스와의 연결을 나타내며, SQL 문을 실행할 수 있는 객체를 생성
    ```java
    Statement statement = connection.createStatement();
    ```

3. Statement: SQL 문을 실행하고 결과를 반환
    ```java
    ResultSet resultSet = statement.executeQuery("SELECT * FROM employees");
    ```

4. ResultSet: SQL 쿼리의 결과를 저장하고 탐색
    ```java
    while (resultSet.next()) {
        int id = resultSet.getInt("id");
        String name = resultSet.getString("name");
    }
    ```

> ### 왜 사용해야 하는가?
1. **데이터베이스 연동**: JDBC를 사용하면 자바 애플리케이션에서 다양한 데이터베이스와 연동할 수 있음
2. **표준화된 API**: JDBC는 표준화된 API를 제공하여 데이터베이스 작업을 쉽게 수행할 수 있음
3. **확장성**: 다양한 데이터베이스 드라이버를 통해 여러 종류의 데이터베이스와 호환 가능

> ### 쉬운 요약
1. JDBC는 "자바에서 데이터베이스에 접속하고 SQL 쿼리를 실행하기 위한 API"
    - DriverManager, Connection, Statement, ResultSet 등이 주요 구성 요소

2. 데이터베이스와의 연결 설정, SQL 문 실행, 결과 처리에 사용

> ### 비유
1. 전화 연결
    - JDBC는 전화 연결에서 "전화번호를 걸고 통화하는 과정"과 같음
    - 예: 전화번호를 걸고, 통화하고, 통화 내용을 듣고 말하는 과정

2. 우편 서비스
    - JDBC는 우편 서비스에서 "편지를 작성하고, 보내고, 받는 과정"과 같음
    - 예: 편지를 작성하고, 우체국에 보내고, 수신자가 편지를 받는 과정

## 추가 자료
1. [JDBC Connection 클래스: 데이터베이스와의 연결을 나타내는 클래스](Connection.md)
2. [JDBC Statement 클래스: SQL 문을 실행하고 결과를 반환하는 클래스](Statement.md)
3. [JDBC PreparedStatement 클래스: 파라미터가 포함된 SQL 문을 실행하는 클래스](PreparedStatement.md)
4. [JDBC ResultSet 클래스: SQL 쿼리의 결과를 저장하고 탐색하는 클래스](ResultSet.md)

[뒤로](/README.md)
