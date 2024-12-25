## JOIN
> ### JOIN이란?
JOIN은 데이터베이스에서 두 개 이상의 테이블을 결합하여 관련된 데이터를 검색하는 데 사용되는 명령어</br>
주로 SELECT 문에서 사용

> ### JOIN의 종류
1. INNER JOIN: 두 테이블에서 일치하는 데이터를 결합
    ```sql
    SELECT employees.name, departments.department_name
    FROM employees
    INNER JOIN departments ON employees.department_id = departments.id;
    ```

2. LEFT JOIN: 왼쪽 테이블의 모든 데이터와 오른쪽 테이블에서 일치하는 데이터를 결합
    ```sql
    SELECT employees.name, departments.department_name
    FROM employees
    LEFT JOIN departments ON employees.department_id = departments.id;
    ```

3. RIGHT JOIN: 오른쪽 테이블의 모든 데이터와 왼쪽 테이블에서 일치하는 데이터를 결합
    ```sql
    SELECT employees.name, departments.department_name
    FROM employees
    RIGHT JOIN departments ON employees.department_id = departments.id;
    ```

4. FULL JOIN: 두 테이블에서 일치하는 모든 데이터를 결합
    ```sql
    SELECT employees.name, departments.department_name
    FROM employees
    FULL JOIN departments ON employees.department_id = departments.id;
    ```

> ### 코드로 보기
1. INNER JOIN 사용
- 직원과 부서 테이블을 결합하여 직원 이름과 부서 이름을 가져옴
    ```sql
    SELECT employees.name, departments.department_name
    FROM employees
    INNER JOIN departments ON employees.department_id = departments.id;
    ```

2. LEFT JOIN 사용
- 직원 테이블의 모든 데이터와 부서 테이블에서 일치하는 데이터를 결합
    ```sql
    SELECT employees.name, departments.department_name
    FROM employees
    LEFT JOIN departments ON employees.department_id = departments.id;
    ```

> ### 쉬운 요약
1. JOIN은 "두 개 이상의 테이블을 결합하여 관련된 데이터를 검색하는 명령어"
    - 주로 SELECT 문에서 사용

2. 다양한 JOIN 종류 제공
    - INNER JOIN, LEFT JOIN, RIGHT JOIN, FULL JOIN 등을 사용하여 데이터를 결합할 수 있음

> ### 비유
1. 서점에서 책과 저자 정보 결합
    - JOIN은 서점에서 "책 정보와 저자 정보를 결합하여 책 제목과 저자 이름을 가져오는 작업"
    - 예: SELECT books.title, authors.name FROM books INNER JOIN authors ON books.author_id = authors.id;

2. 음식점에서 메뉴와 카테고리 정보 결합
    - 데이터베이스가 음식점 메뉴라면, JOIN은 메뉴판에서 "메뉴 정보와 카테고리 정보를 결합하여 메뉴 이름과 카테고리 이름을 가져오는 작업"
    - 예: SELECT menu.name, categories.category_name FROM menu INNER JOIN categories ON menu.category_id = categories.id;

[뒤로](mysql.md)
