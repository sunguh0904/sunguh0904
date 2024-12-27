## JDBC ResultSet Class
> ### ResultSet이란?
ResultSet은 JDBC에서 SQL 쿼리의 결과를 저장하고 탐색하는 데 사용하는 클래스</br>
데이터베이스에서 조회한 결과를 테이블 형식으로 저장하고, 이를 탐색하면서 데이터를 읽어올 수 있음

> ### ResultSet의 주요 기능
1. 결과 탐색: SQL 쿼리의 결과를 한 행씩 탐색
    ```java
    // ResultSet 객체를 사용하여 결과를 탐색
    while (resultSet.next()) {
        int id = resultSet.getInt("id");
        String name = resultSet.getString("name");
        // 결과 처리 로직
    }
    ```

2. 데이터 읽기: 각 열의 데이터를 읽음
    ```java
    int id = resultSet.getInt("id"); // 정수형 데이터 읽기
    String name = resultSet.getString("name"); // 문자열 데이터 읽기
    ```

3. 커서 이동: 커서를 사용하여 결과 집합 내에서 이동
    ```java
    resultSet.beforeFirst(); // 첫 번째 행 이전으로 이동
    resultSet.afterLast(); // 마지막 행 이후로 이동
    resultSet.absolute(3); // 세 번째 행으로 이동
    ```

4. 메타데이터 읽기: 결과 집합의 메타데이터를 읽음
    ```java
    ResultSetMetaData metaData = resultSet.getMetaData();
    int columnCount = metaData.getColumnCount(); // 열의 개수 읽기
    String columnName = metaData.getColumnName(1); // 첫 번째 열의 이름 읽기
    ```

> ### 왜 사용해야 하는가?
1. **결과 탐색**: ResultSet을 사용하면 SQL 쿼리의 결과를 한 행씩 탐색할 수 있음
2. **데이터 읽기**: 각 열의 데이터를 읽어와서 처리할 수 있음
3. **커서 이동**: 커서를 사용하여 결과 집합 내에서 자유롭게 이동할 수 있음

> ### 쉬운 요약
1. ResultSet은 "SQL 쿼리의 결과를 저장하고 탐색하는 클래스"
    - 결과 탐색, 데이터 읽기, 커서 이동, 메타데이터 읽기 기능을 제공

> ### 비유
1. 엑셀 시트
    - ResultSet은 "엑셀 시트에서 데이터를 한 셀씩 읽어오는 과정"과 같음
    - 예: 엑셀 시트의 각 셀을 읽어와서 데이터를 처리

2. 책 읽기
    - ResultSet은 "책을 한 페이지씩 넘기면서 읽는 과정"과 같음
    - 예: 책의 각 페이지를 넘기면서 내용을 읽어오는 과정

[뒤로](JDBC.md)
