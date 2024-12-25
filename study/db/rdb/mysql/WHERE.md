## WHERE
> ### WHERE란?
WHERE는 데이터베이스에서 조건에 맞는 데이터를 선택하는 데 사용되는 절</br>
주로 SELECT, UPDATE, DELETE 문에서 사용

> ### WHERE의 종류
1. 특정 조건에 맞는 데이터 선택
    ```sql
    SELECT * FROM employees WHERE department = 'Sales';
    ```

2. 여러 조건을 결합하여 데이터 선택
    ```sql
    SELECT * FROM employees WHERE department = 'Sales' AND age > 30;
    ```

> ### 왜 사용해야 하는가?
1. **조건부 데이터 조회**: WHERE를 사용하면 특정 조건에 맞는 데이터를 조회할 수 있음
2. **데이터 필터링**: WHERE를 사용하여 데이터를 필터링하고 필요한 정보를 추출할 수 있음

> ### 쉬운 요약
1. WHERE는 "조건에 맞는 데이터를 선택하는 절"
    - 주로 SELECT, UPDATE, DELETE 문에서 사용

2. 여러 조건을 결합하여 데이터 선택 가능
    - 특정 조건 또는 여러 조건을 결합하여 데이터를 필터링할 수 있음

> ### 비유
1. 서점에서 특정 주제의 책 찾기
    - WHERE는 서점에서 "특정 주제의 책"을 찾는 작업
    - 예: SELECT * FROM books WHERE genre = 'Science Fiction';

2. 음식점에서 특정 재료가 포함된 메뉴 선택
    - WHERE는 메뉴판에서 "특정 재료가 포함된 음식"을 선택하는 작업
    - 예: SELECT * FROM menu WHERE ingredients LIKE '%chicken%';

[뒤로](mysql.md)
