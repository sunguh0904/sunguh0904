## SUBQUERIES
> ### SUBQUERIES란?
SUBQUERIES는 다른 쿼리 내에 포함된 쿼리로, 주로 SELECT, INSERT, UPDATE, DELETE 문에서 사용</br>
서브쿼리는 메인 쿼리의 조건을 지정하거나 데이터를 필터링하는 데 사용

> ### SUBQUERIES의 예
1. SELECT 문에서 서브쿼리 사용
- 급여가 평균 급여보다 높은 직원 선택
    ```sql
    SELECT * FROM employees WHERE salary > (SELECT AVG(salary) FROM employees);
    ```

2. INSERT 문에서 서브쿼리 사용
- 다른 테이블에서 데이터를 가져와 새로운 테이블에 삽입
    ```sql
    INSERT INTO high_salary_employees (name, salary)
    SELECT name, salary FROM employees WHERE salary > 5000;
    ```

3. UPDATE 문에서 서브쿼리 사용
- 특정 조건을 만족하는 데이터를 업데이트
    ```sql
    UPDATE employees SET salary = salary * 1.1
    WHERE department_id = (SELECT id FROM departments WHERE name = 'HR');
    ```

4. DELETE 문에서 서브쿼리 사용
- 특정 조건을 만족하는 데이터를 삭제
    ```sql
    DELETE FROM employees WHERE department_id = (SELECT id FROM departments WHERE name = 'HR');
    ```

> ### 코드로 보기
1. 기본 서브쿼리 사용
- 급여가 평균 급여보다 높은 직원 선택
    ```sql
    SELECT * FROM employees WHERE salary > (SELECT AVG(salary) FROM employees);
    ```

2. 서브쿼리를 사용한 데이터 삽입
- 급여가 5000 이상인 직원을 high_salary_employees 테이블에 삽입
    ```sql
    INSERT INTO high_salary_employees (name, salary)
    SELECT name, salary FROM employees WHERE salary > 5000;
    ```

> ### 쉬운 요약
1. SUBQUERIES는 "다른 쿼리 내에 포함된 쿼리"
    - 주로 메인 쿼리의 조건을 지정하거나 데이터를 필터링하는 데 사용

2. 다양한 문장에서 사용 가능
    - SELECT, INSERT, UPDATE, DELETE 문에서 서브쿼리를 사용할 수 있음

> ### 비유
1. 서점에서 특정 조건의 책 찾기
    - SUBQUERIES는 서점에서 "특정 저자의 책 중에서 가장 많이 팔린 책"을 찾는 작업
    - 예: SELECT * FROM books WHERE sales = (SELECT MAX(sales) FROM books WHERE author = '홍길동');

2. 음식점에서 특정 조건의 메뉴 선택
    - 데이터베이스가 음식점 메뉴라면, SUBQUERIES는 메뉴판에서 "특정 카테고리의 음식 중에서 가장 인기 있는 음식"을 선택하는 작업
    - 예: SELECT * FROM menu WHERE popularity = (SELECT MAX(popularity) FROM menu WHERE category = '디저트');

[뒤로](mysql.md)
