## SET OPERATORS
> ### SET OPERATORS란?
SET OPERATORS는 두 개 이상의 쿼리 결과를 결합하여 하나의 결과 집합으로 만드는 데 사용되는 연산자</br>
주로 UNION, UNION ALL, INTERSECT, EXCEPT 등이 있음

> ### SET OPERATORS의 종류
1. UNION: 두 쿼리의 결과를 결합하고 중복된 행을 제거
    ```sql
    SELECT name FROM employees
    UNION
    SELECT name FROM managers;
    ```

2. UNION ALL: 두 쿼리의 결과를 결합하고 중복된 행을 포함
    ```sql
    SELECT name FROM employees
    UNION ALL
    SELECT name FROM managers;
    ```

3. INTERSECT: 두 쿼리의 결과에서 공통된 행을 반환
    ```sql
    SELECT name FROM employees
    INTERSECT
    SELECT name FROM managers;
    ```

4. EXCEPT: 첫 번째 쿼리의 결과에서 두 번째 쿼리의 결과를 제외한 행을 반환
    ```sql
    SELECT name FROM employees
    EXCEPT
    SELECT name FROM managers;
    ```

> ### 코드로 보기
1. UNION 사용
- 직원과 관리자 테이블에서 고유한 이름을 결합
    ```sql
    SELECT name FROM employees
    UNION
    SELECT name FROM managers;
    ```

2. UNION ALL 사용
- 직원과 관리자 테이블에서 모든 이름을 결합
    ```sql
    SELECT name FROM employees
    UNION ALL
    SELECT name FROM managers;
    ```

3. INTERSECT 사용
- 직원과 관리자 테이블에서 공통된 이름을 반환
    ```sql
    SELECT name FROM employees
    INTERSECT
    SELECT name FROM managers;
    ```

4. EXCEPT 사용
- 직원 테이블에서 관리자 테이블에 없는 이름을 반환
    ```sql
    SELECT name FROM employees
    EXCEPT
    SELECT name FROM managers;
    ```

> ### 쉬운 요약
1. SET OPERATORS는 "두 개 이상의 쿼리 결과를 결합하는 연산자"
    - 주로 UNION, UNION ALL, INTERSECT, EXCEPT 등이 있음

2. 중복된 행 포함 여부에 따라 선택 가능
    - UNION은 중복된 행을 제거하고, UNION ALL은 중복된 행을 포함

> ### 비유
1. 서점에서 두 개 이상의 책 목록 결합
    - SET OPERATORS는 서점에서 "두 개 이상의 책 목록을 결합하여 하나의 목록으로 만드는 작업"
    - 예: SELECT title FROM fiction_books UNION SELECT title FROM non_fiction_books;

2. 음식점에서 두 개 이상의 메뉴 목록 결합
    - 데이터베이스가 음식점 메뉴라면, SET OPERATORS는 메뉴판에서 "두 개 이상의 메뉴 목록을 결합하여 하나의 목록으로 만드는 작업"
    - 예: SELECT name FROM breakfast_menu UNION SELECT name FROM lunch_menu;

[뒤로](mysql.md)
