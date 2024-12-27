## 집합 연산자
> ### 집합 연산자란?
집합 연산자는 데이터베이스에서 여러 쿼리의 결과를 결합하거나 비교하는 데 사용되는 연산자</br>
주로 SELECT 문에서 사용

> ### 집합 연산자의 주요 기능
1. UNION: 두 쿼리의 결과를 결합하고 중복을 제거
    ```sql
    -- employees와 managers 테이블에서 name 열을 결합하고 중복을 제거하여 조회
    SELECT name FROM employees
    UNION
    SELECT name FROM managers;
    ```

2. UNION ALL: 두 쿼리의 결과를 결합하고 중복을 포함
    ```sql
    -- employees와 managers 테이블에서 name 열을 결합하고 중복을 포함하여 조회
    SELECT name FROM employees
    UNION ALL
    SELECT name FROM managers;
    ```

3. INTERSECT: 두 쿼리의 결과에서 공통된 데이터를 선택
    ```sql
    -- employees와 managers 테이블에서 공통된 name 열을 조회
    SELECT name FROM employees
    INTERSECT
    SELECT name FROM managers;
    ```

4. EXCEPT: 첫 번째 쿼리의 결과에서 두 번째 쿼리의 결과를 제외한 데이터를 선택
    ```sql
    -- employees 테이블에서 managers 테이블에 없는 name 열을 조회
    SELECT name FROM employees
    EXCEPT
    SELECT name FROM managers;
    ```

> ### 왜 사용해야 하는가?
1. **데이터 결합 및 비교**: 집합 연산자를 사용하면 여러 쿼리의 결과를 결합하거나 비교할 수 있음
2. **데이터 분석**: 집합 연산자를 사용하여 데이터를 결합하고 분석할 수 있음

> ### 쉬운 요약
1. 집합 연산자는 "여러 쿼리의 결과를 결합하거나 비교하는 연산자"
    - 주로 SELECT 문에서 사용

2. UNION, UNION ALL, INTERSECT, EXCEPT 등의 연산자 제공
    - 여러 쿼리의 결과를 결합하거나 비교할 수 있음

> ### 비유
1. 서점에서 여러 목록의 책 결합
    - 집합 연산자는 서점에서 "여러 목록의 책을 결합하거나 비교"하는 작업
    - 예: SELECT title FROM fiction_books UNION SELECT title FROM non_fiction_books;

2. 음식점에서 여러 목록의 메뉴 결합
    - 집합 연산자는 메뉴판에서 "여러 목록의 메뉴를 결합하거나 비교"하는 작업
    - 예: SELECT name FROM breakfast_menu UNION SELECT name FROM lunch_menu;

[뒤로](mysql.md)
