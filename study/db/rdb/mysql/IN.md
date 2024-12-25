## IN
> ### IN이란?
IN은 데이터베이스에서 특정 값 목록에 포함된 데이터를 선택하는 데 사용되는 연산자</br>
주로 WHERE 절에서 사용

> ### IN의 종류
1. 특정 값 목록에 포함된 데이터 선택
    ```sql
    SELECT * FROM employees WHERE department IN ('Sales', 'Marketing');
    ```

2. 서브쿼리를 사용한 IN
    ```sql
    SELECT * FROM employees WHERE department_id IN (SELECT id FROM departments WHERE location = 'New York');
    ```

> ### 왜 사용해야 하는가?
1. **조건부 데이터 조회**: IN을 사용하면 특정 값 목록에 포함된 데이터를 쉽게 조회할 수 있음
2. **데이터 필터링**: IN을 사용하여 데이터를 필터링하고 필요한 정보를 추출할 수 있음

> ### 쉬운 요약
1. IN은 "특정 값 목록에 포함된 데이터를 선택하는 연산자"
    - 주로 WHERE 절에서 사용

2. 서브쿼리와 함께 사용 가능
    - 서브쿼리를 사용하여 동적으로 값 목록을 생성할 수 있음

> ### 비유
1. 서점에서 특정 저자의 책 찾기
    - IN은 서점에서 "특정 저자의 책"을 찾는 작업
    - 예: SELECT * FROM books WHERE author IN ('Author A', 'Author B');

2. 음식점에서 특정 재료가 포함된 메뉴 선택
    - IN은 메뉴판에서 "특정 재료가 포함된 음식"을 선택하는 작업
    - 예: SELECT * FROM menu WHERE ingredient IN ('Chicken', 'Beef');

[뒤로](mysql.md)
