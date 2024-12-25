## DML
> ### DML이란?
DML(Data Manipulation Language)은 데이터베이스에서 데이터를 조작하는 데 사용되는 언어</br>
주로 SELECT, INSERT, UPDATE, DELETE 등이 있음

> ### DML의 종류
1. SELECT: 데이터를 조회
    ```sql
    SELECT * FROM employees;
    ```

2. INSERT: 데이터를 추가
    ```sql
    INSERT INTO employees (id, name, position) VALUES (1, 'John Doe', 'Manager');
    ```

3. UPDATE: 데이터를 수정
    ```sql
    UPDATE employees SET position = 'Senior Manager' WHERE id = 1;
    ```

4. DELETE: 데이터를 삭제
    ```sql
    DELETE FROM employees WHERE id = 1;
    ```

> ### 왜 사용해야 하는가?
1. **데이터 조작**: DML을 사용하면 데이터베이스의 데이터를 조회, 추가, 수정, 삭제할 수 있음
2. **데이터 관리**: DML을 사용하여 데이터를 효율적으로 관리하고 필요한 정보를 추출할 수 있음

> ### 쉬운 요약
1. DML은 "데이터베이스에서 데이터를 조작하는 언어"
    - 주로 SELECT, INSERT, UPDATE, DELETE 등이 있음

2. 데이터를 조회, 추가, 수정, 삭제하는 데 사용

> ### 비유
1. 도서관에서 책 관리
    - DML은 도서관에서 "책을 조회, 추가, 수정, 삭제하는 작업"과 같음
    - 예: 새로운 책을 추가하거나, 기존 책의 정보를 수정

2. 음식점에서 메뉴 관리
    - DML은 음식점에서 "메뉴를 조회, 추가, 수정, 삭제하는 작업"과 같음
    - 예: 새로운 메뉴를 추가하거나, 기존 메뉴의 가격을 수정

[뒤로](mysql.md)
