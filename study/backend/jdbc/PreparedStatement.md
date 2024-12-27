## JDBC PreparedStatement Class
> ### PreparedStatement 클래스란?
PreparedStatement 클래스는 JDBC에서 파라미터가 포함된 SQL 문을 실행하기 위해 사용되는 클래스입니다. 이 클래스는 SQL 문을 미리 컴파일하고, 실행 시 파라미터를 바인딩하여 성능을 향상시키고 SQL 인젝션 공격을 방지합니다.

> ### PreparedStatement 클래스의 주요 기능
1. SQL 문 준비: 파라미터가 포함된 SQL 문을 미리 컴파일합니다.
    ```java
    // 파라미터가 포함된 SQL 문을 준비
    PreparedStatement preparedStatement = connection.prepareStatement("SELECT * FROM employees WHERE id = ?");
    ```

2. 파라미터 바인딩: SQL 문 실행 전에 파라미터 값을 설정합니다.
    ```java
    // 첫 번째 파라미터에 값을 설정
    preparedStatement.setInt(1, 1);
    ```

3. SQL 문 실행: SQL 문을 실행하고 결과를 반환합니다.
    ```java
    // SQL SELECT 문을 실행하고 결과를 반환
    ResultSet resultSet = preparedStatement.executeQuery();
    
    // SQL INSERT, UPDATE, DELETE 문을 실행하고 영향을 받은 행 수를 반환
    int rowsAffected = preparedStatement.executeUpdate();
    ```

4. 결과 처리: SQL 쿼리의 결과를 ResultSet 객체로 반환받아 처리합니다.
    ```java
    // ResultSet 객체를 사용하여 결과를 탐색
    while (resultSet.next()) {
        int id = resultSet.getInt("id");
        String name = resultSet.getString("name");
        // 결과 처리 로직
    }
    ```

> ### 왜 사용해야 하는가?
1. **성능 향상**: SQL 문을 미리 컴파일하여 실행 시 성능을 향상시킬 수 있음
2. **SQL 인젝션 방지**: 파라미터 바인딩을 통해 SQL 인젝션 공격을 방지할 수 있음
3. **가독성 향상**: 파라미터가 포함된 SQL 문을 사용하여 코드의 가독성을 향상시킬 수 있음

> ### 쉬운 요약
1. PreparedStatement 클래스는 "파라미터가 포함된 SQL 문을 실행하기 위한 클래스"
    - SQL 문 준비, 파라미터 바인딩, SQL 문 실행, 결과 처리 기능을 제공

> ### 비유
1. 템플릿
    - PreparedStatement 클래스는 "미리 준비된 템플릿에 값을 채워 넣는 과정"과 같음
    - 예: 템플릿에 값을 채워 넣어 최종 문서를 완성하는 과정

2. 주문서
    - PreparedStatement 클래스는 "미리 작성된 주문서에 필요한 정보를 채워 넣는 과정"과 같음
    - 예: 주문서에 고객 정보를 채워 넣어 주문을 완료하는 과정

[뒤로](JDBC.md)
