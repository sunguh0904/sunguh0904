## DML (Data Manipulation Language)
> ### DML이란?
DML은 데이터베이스에서 데이터를 조작하는 데 사용되는 언어</br>
주로 데이터를 삽입, 업데이트, 삭제, 조회하는 데 사용</br>
DML에는 INSERT, UPDATE, DELETE, SELECT 명령어가 포함

> ### DML의 종류
1. INSERT: 데이터를 테이블에 삽입
    ```sql
    INSERT INTO employees (name, age, department) VALUES ('John Doe', 30, 'HR');
    ```

2. UPDATE: 테이블의 데이터를 업데이트
    ```sql
    UPDATE employees SET age = 31 WHERE name = 'John Doe';
    ```

3. DELETE: 테이블의 데이터를 삭제
    ```sql
    DELETE FROM employees WHERE name = 'John Doe';
    ```

4. SELECT: 테이블의 데이터를 조회
    ```sql
    SELECT * FROM employees;
    ```

> ### 코드로 보기
1. INSERT 사용
- 새로운 직원 데이터를 테이블에 삽입
    ```sql
    INSERT INTO employees (name, age, department) VALUES ('Jane Smith', 28, 'Engineering');
    ```

2. UPDATE 사용
- 특정 직원의 부서를 업데이트
    ```sql
    UPDATE employees SET department = 'Marketing' WHERE name = 'Jane Smith';
    ```

3. DELETE 사용
- 특정 직원 데이터를 삭제
    ```sql
    DELETE FROM employees WHERE name = 'Jane Smith';
    ```

4. SELECT 사용
- 모든 직원 데이터를 조회
    ```sql
    SELECT * FROM employees;
    ```

> ### 쉬운 요약
1. DML은 "데이터를 조작하는 언어"
    - 데이터를 삽입, 업데이트, 삭제, 조회하는 데 사용

2. 다양한 명령어 제공
    - INSERT, UPDATE, DELETE, SELECT 명령어가 포함됨

> ### 비유
1. 서점에서 책 관리
    - DML은 서점에서 "새로운 책을 추가하고(INSERT), 책 정보를 업데이트하며(UPDATE), 책을 삭제하고(DELETE), 책 목록을 조회하는(SELECT) 작업"
    - 예: INSERT INTO books (title, author) VALUES ('New Book', 'Author Name');

2. 음식점에서 메뉴 관리
    - 데이터베이스가 음식점 메뉴라면, DML은 메뉴판에서 "새로운 메뉴를 추가하고(INSERT), 메뉴 정보를 업데이트하며(UPDATE), 메뉴를 삭제하고(DELETE), 메뉴 목록을 조회하는(SELECT) 작업"
    - 예: INSERT INTO menu (name, price) VALUES ('New Dish', 15.99);

[뒤로](mysql.md)
