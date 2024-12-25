## SELECT
> ### SELECT란?
SELECT는 데이터베이스에서 데이터를 조회하는 데 사용되는 SQL 명령어</br>
주로 테이블에서 원하는 데이터를 선택하여 반환하는 데 사용됨

> ### SELECT의 종류
1. 기본 SELECT: 테이블의 모든 열을 조회
    ```sql
    SELECT * FROM employees;
    ```

2. 특정 열 SELECT: 테이블의 특정 열을 조회
    ```sql
    SELECT name, position FROM employees;
    ```

3. 조건부 SELECT: 특정 조건을 만족하는 데이터를 조회
    ```sql
    SELECT name, position FROM employees WHERE department = 'Sales';
    ```

4. 정렬된 SELECT: 데이터를 특정 열을 기준으로 정렬하여 조회
    ```sql
    SELECT name, position FROM employees ORDER BY name ASC;
    ```

> ### 왜 사용해야 하는가?
1. **데이터 조회**: SELECT를 사용하면 데이터베이스에서 원하는 데이터를 조회할 수 있음
2. **데이터 분석**: SELECT를 사용하여 데이터를 분석하고 필요한 정보를 추출할 수 있음
3. **데이터 검증**: SELECT를 사용하여 데이터의 정확성과 일관성을 검증할 수 있음

> ### 쉬운 요약
1. SELECT는 "데이터베이스에서 데이터를 조회하는 SQL 명령어"
    - 주로 테이블에서 원하는 데이터를 선택하여 반환하는 데 사용됨

2. 기본 SELECT, 특정 열 SELECT, 조건부 SELECT, 정렬된 SELECT 등이 있음

> ### 비유
1. 도서관에서 책 찾기
    - SELECT는 도서관에서 "원하는 책을 찾는 것"과 같음
    - 예: 특정 주제의 책을 찾기 위해 도서관 카탈로그를 검색

2. 메뉴에서 음식 선택
    - SELECT는 레스토랑에서 "메뉴에서 원하는 음식을 선택하는 것"과 같음
    - 예: 메뉴에서 특정 요리를 선택하여 주문

[뒤로](mysql.md)