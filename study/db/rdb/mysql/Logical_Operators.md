## 논리 연산자
> ### 논리 연산자란?
논리 연산자는 데이터베이스에서 여러 조건을 결합하여 사용되는 연산자</br>
주로 WHERE 절에서 사용

> ### 논리 연산자의 주요 기능
1. AND: 모든 조건이 참인 데이터를 선택
    ```sql
    -- department가 'Sales'이고 age가 30보다 큰 데이터를 조회
    SELECT * FROM employees WHERE department = 'Sales' AND age > 30;
    ```

2. OR: 하나 이상의 조건이 참인 데이터를 선택
    ```sql
    -- department가 'Sales'이거나 age가 30보다 큰 데이터를 조회
    SELECT * FROM employees WHERE department = 'Sales' OR age > 30;
    ```

3. NOT: 조건이 거짓인 데이터를 선택
    ```sql
    -- department가 'Sales'가 아닌 데이터를 조회
    SELECT * FROM employees WHERE NOT department = 'Sales';
    ```

> ### 왜 사용해야 하는가?
1. **조건 결합**: 논리 연산자를 사용하면 여러 조건을 결합하여 데이터를 조회할 수 있음
2. **데이터 필터링**: 논리 연산자를 사용하여 데이터를 필터링하고 필요한 정보를 추출할 수 있음

> ### 쉬운 요약
1. 논리 연산자는 "여러 조건을 결합하여 사용하는 연산자"
    - 주로 WHERE 절에서 사용

2. AND, OR, NOT 등의 연산자 제공
    - 여러 조건을 결합하여 데이터를 필터링할 수 있음

> ### 비유
1. 서점에서 여러 조건의 책 찾기
    - 논리 연산자는 서점에서 "여러 조건의 책"을 찾는 작업
    - 예: SELECT * FROM books WHERE genre = 'Science Fiction' AND price < 20000;

2. 음식점에서 여러 조건의 메뉴 선택
    - 논리 연산자는 메뉴판에서 "여러 조건의 음식"을 선택하는 작업
    - 예: SELECT * FROM menu WHERE category = 'Dessert' OR calories < 500;

[뒤로](mysql.md)
