## MySQL SELECT
> ### SELECT란?
SELECT는 MySQL에서 데이터를 조회하는 데 사용하는 명령어</br>
데이터베이스에서 원하는 데이터를 선택하고, 이를 조회할 수 있음

> ### SELECT의 주요 기능
1. 모든 데이터 조회: 테이블의 모든 데이터를 조회
    ```sql
    -- employees 테이블의 모든 데이터를 조회
    SELECT * FROM employees;
    ```

2. 특정 열 조회: 특정 열만 선택하여 조회
    ```sql
    -- employees 테이블에서 name과 position 열만 조회
    SELECT name, position FROM employees;
    ```

3. 조건부 조회: WHERE 절을 사용하여 조건에 맞는 데이터만 조회
    ```sql
    -- position이 'Manager'인 데이터만 조회
    SELECT * FROM employees WHERE position = 'Manager';
    ```

4. 정렬: ORDER BY 절을 사용하여 데이터를 정렬
    ```sql
    -- salary를 기준으로 내림차순 정렬하여 조회
    SELECT * FROM employees ORDER BY salary DESC;
    ```

5. 제한: LIMIT 절을 사용하여 조회할 데이터의 수를 제한
    ```sql
    -- 최대 5개의 데이터만 조회
    SELECT * FROM employees LIMIT 5;
    ```

> ### 왜 사용해야 하는가?
1. **데이터 조회**: SELECT를 사용하면 데이터베이스에서 원하는 데이터를 조회할 수 있음
2. **조건부 조회**: WHERE 절을 사용하여 조건에 맞는 데이터만 조회할 수 있음
3. **정렬 및 제한**: ORDER BY와 LIMIT 절을 사용하여 데이터를 정렬하고 조회할 데이터의 수를 제한할 수 있음

> ### 쉬운 요약
1. SELECT는 "데이터베이스에서 데이터를 조회하는 명령어"
    - 모든 데이터 조회, 특정 열 조회, 조건부 조회, 정렬, 제한 기능을 제공

> ### 비유
1. 도서관에서 책 찾기
    - SELECT는 "도서관에서 원하는 책을 찾는 과정"과 같음
    - 예: 모든 책을 조회하거나, 특정 주제의 책만 선택하여 조회

2. 메뉴에서 음식 선택
    - SELECT는 "레스토랑 메뉴에서 원하는 음식을 선택하는 과정"과 같음
    - 예: 모든 음식을 조회하거나, 특정 종류의 음식만 선택하여 조회

[뒤로](mysql.md)