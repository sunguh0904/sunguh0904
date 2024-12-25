## JOIN
> ### JOIN이란?
JOIN은 데이터베이스에서 여러 테이블의 데이터를 결합하여 조회하는 데 사용되는 연산자</br>
주로 SELECT 문에서 사용

> ### JOIN의 종류
1. INNER JOIN: 두 테이블에서 일치하는 데이터를 조회
    ```sql
    SELECT employees.name, departments.name
    FROM employees
    INNER JOIN departments ON employees.department_id = departments.id;
    ```

2. LEFT JOIN: 왼쪽 테이블의 모든 데이터와 오른쪽 테이블에서 일치하는 데이터를 조회
    ```sql
    SELECT employees.name, departments.name
    FROM employees
    LEFT JOIN departments ON employees.department_id = departments.id;
    ```

3. RIGHT JOIN: 오른쪽 테이블의 모든 데이터와 왼쪽 테이블에서 일치하는 데이터를 조회
    ```sql
    SELECT employees.name, departments.name
    FROM employees
    RIGHT JOIN departments ON employees.department_id = departments.id;
    ```

4. FULL JOIN: 두 테이블에서 일치하는 데이터와 일치하지 않는 모든 데이터를 조회
    ```sql
    SELECT employees.name, departments.name
    FROM employees
    FULL JOIN departments ON employees.department_id = departments.id;
    ```

> ### 왜 사용해야 하는가?
1. **데이터 결합**: JOIN을 사용하면 여러 테이블의 데이터를 결합하여 조회할 수 있음
2. **데이터 분석**: JOIN을 사용하여 여러 테이블의 데이터를 결합하고 분석할 수 있음

> ### 쉬운 요약
1. JOIN은 "여러 테이블의 데이터를 결합하여 조회하는 연산자"
    - 주로 SELECT 문에서 사용

2. INNER JOIN, LEFT JOIN, RIGHT JOIN, FULL JOIN 등이 있음

> ### 비유
1. 도서관에서 여러 책의 정보를 결합하여 조회
    - JOIN은 도서관에서 "여러 책의 정보를 결합하여 조회"하는 작업
    - 예: SELECT books.title, authors.name FROM books INNER JOIN authors ON books.author_id = authors.id;

2. 음식점에서 여러 메뉴의 정보를 결합하여 조회
    - JOIN은 메뉴판에서 "여러 메뉴의 정보를 결합하여 조회"하는 작업
    - 예: SELECT menu.name, categories.name FROM menu INNER JOIN categories ON menu.category_id = categories.id;

[뒤로](mysql.md)
