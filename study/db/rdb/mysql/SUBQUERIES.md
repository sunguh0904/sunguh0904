## 서브쿼리
> ### 서브쿼리란?
서브쿼리는 다른 쿼리 내에 포함된 쿼리</br>
주로 SELECT, INSERT, UPDATE, DELETE 문에서 사용

> ### 서브쿼리의 주요 기능
1. SELECT 문에서 서브쿼리 사용: 다른 쿼리의 결과를 조건으로 사용
    ```sql
    -- department_id가 'Sales' 부서의 id와 일치하는 데이터를 조회
    SELECT * FROM employees WHERE department_id = (SELECT id FROM departments WHERE name = 'Sales');
    ```

2. INSERT 문에서 서브쿼리 사용: 다른 쿼리의 결과를 삽입할 데이터로 사용
    ```sql
    -- 'Sales' 부서의 id를 사용하여 새로운 직원 데이터를 삽입
    INSERT INTO employees (name, department_id)
    SELECT 'John Doe', id FROM departments WHERE name = 'Sales';
    ```

3. UPDATE 문에서 서브쿼리 사용: 다른 쿼리의 결과를 업데이트할 데이터로 사용
    ```sql
    -- 'John Doe'의 department_id를 'Marketing' 부서의 id로 업데이트
    UPDATE employees SET department_id = (SELECT id FROM departments WHERE name = 'Marketing') WHERE name = 'John Doe';
    ```

4. DELETE 문에서 서브쿼리 사용: 다른 쿼리의 결과를 삭제할 데이터로 사용
    ```sql
    -- department_id가 'Sales' 부서의 id와 일치하는 데이터를 삭제
    DELETE FROM employees WHERE department_id = (SELECT id FROM departments WHERE name = 'Sales');
    ```

> ### 왜 사용해야 하는가?
1. **복잡한 쿼리 작성**: 서브쿼리를 사용하면 복잡한 쿼리를 쉽게 작성할 수 있음
2. **데이터 필터링**: 서브쿼리를 사용하여 데이터를 필터링하고 필요한 정보를 추출할 수 있음

> ### 쉬운 요약
1. 서브쿼리는 "다른 쿼리 내에 포함된 쿼리"
    - 주로 SELECT, INSERT, UPDATE, DELETE 문에서 사용

2. 다양한 문장에서 사용 가능
    - SELECT, INSERT, UPDATE, DELETE 문에서 서브쿼리를 사용할 수 있음

> ### 비유
1. 서점에서 특정 조건의 책 찾기
    - 서브쿼리는 서점에서 "특정 조건의 책"을 찾는 작업
    - 예: SELECT * FROM books WHERE author_id = (SELECT id FROM authors WHERE name = 'Author A');

2. 음식점에서 특정 조건의 메뉴 선택
    - 서브쿼리는 메뉴판에서 "특정 조건의 음식"을 선택하는 작업
    - 예: SELECT * FROM menu WHERE category_id = (SELECT id FROM categories WHERE name = 'Dessert');

[뒤로](mysql.md)
