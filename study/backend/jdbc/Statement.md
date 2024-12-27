## JDBC Statement Class
> ### Statement 클래스란?
Statement 클래스는 JDBC에서 SQL 문을 실행하고 결과를 반환하는 데 사용되는 클래스입니다. 이 클래스는 데이터베이스와의 연결을 통해 SQL 문을 실행하고, 결과를 처리하는 역할을 합니다.

> ### Statement 클래스의 주요 기능
1. SQL 문 실행: SQL 문을 실행하고 결과를 반환합니다.
    ```java
    // Statement 객체를 사용하여 SQL SELECT 문을 실행
    Statement statement = connection.createStatement();
    ResultSet resultSet = statement.executeQuery("SELECT * FROM employees");
    ```

2. 결과 처리: SQL 쿼리의 결과를 ResultSet 객체로 반환받아 처리합니다.
    ```java
    // ResultSet 객체를 사용하여 결과를 탐색
    while (resultSet.next()) {
        int id = resultSet.getInt("id");
        String name = resultSet.getString("name");
        // 결과 처리 로직
    }
    ```

3. SQL 문 실행 (INSERT, UPDATE, DELETE): 데이터베이스에 변경을 가하는 SQL 문을 실행합니다.
    ```java
    // Statement 객체를 사용하여 SQL INSERT 문을 실행
    int rowsInserted = statement.executeUpdate("INSERT INTO employees (name, position, salary) VALUES ('John Doe', 'Manager', 50000)");
    
    // Statement 객체를 사용하여 SQL UPDATE 문을 실행
    int rowsUpdated = statement.executeUpdate("UPDATE employees SET salary = 55000 WHERE id = 1");
    
    // Statement 객체를 사용하여 SQL DELETE 문을 실행
    int rowsDeleted = statement.executeUpdate("DELETE FROM employees WHERE id = 1");
    ```

4. 배치 처리: 여러 개의 SQL 문을 일괄 처리합니다.
    ```java
    // Statement 객체를 사용하여 배치 작업 추가
    statement.addBatch("INSERT INTO employees (name, position, salary) VALUES ('Jane Doe', 'Developer', 60000)");
    statement.addBatch("UPDATE employees SET salary = 65000 WHERE id = 2");
    statement.addBatch("DELETE FROM employees WHERE id = 3");
    
    // 배치 작업 실행
    int[] batchResults = statement.executeBatch();
    ```

> ### 왜 사용해야 하는가?
1. **SQL 문 실행**: Statement 클래스를 사용하면 데이터베이스에 SQL 문을 실행하고 결과를 처리할 수 있음
2. **결과 처리**: SQL 쿼리의 결과를 ResultSet 객체로 반환받아 쉽게 처리할 수 있음
3. **배치 처리**: 여러 개의 SQL 문을 일괄 처리하여 성능을 향상시킬 수 있음

> ### 쉬운 요약
1. Statement 클래스는 "SQL 문을 실행하고 결과를 반환하는 클래스"
    - SQL 문 실행, 결과 처리, 배치 처리 기능을 제공

> ### 비유
1. 명령어 실행
    - Statement 클래스는 컴퓨터에서 "명령어를 실행하고 결과를 반환하는 과정"과 같음
    - 예: 명령어를 입력하고, 실행하고, 결과를 확인하는 과정

2. 주문 처리
    - Statement 클래스는 레스토랑에서 "주문을 받고, 요리를 준비하고, 결과를 제공하는 과정"과 같음
    - 예: 주문을 받고, 요리를 준비하고, 손님에게 제공하는 과정

[뒤로](JDBC.md)
