## DISTINCT
> ### DISTINCT란?
DISTINCT는 데이터베이스에서 중복된 값을 제거하고 고유한 값을 선택하는 데 사용되는 명령어</br>
주로 SELECT 문에서 사용

> ### DISTINCT의 예
1. 중복된 값을 제거하고 고유한 값 선택
- 직원 테이블에서 고유한 부서 이름 선택
    ```sql
    SELECT DISTINCT department FROM employees;
    ```

2. 여러 열에서 고유한 값 선택
- 직원 테이블에서 고유한 부서와 직책 조합 선택
    ```sql
    SELECT DISTINCT department, job_title FROM employees;
    ```

> ### 코드로 보기
1. 기본 DISTINCT 문
- 직원 테이블에서 고유한 이름 선택
    ```sql
    SELECT DISTINCT name FROM employees;
    ```

2. 여러 열을 사용한 DISTINCT 문
- 직원 테이블에서 고유한 이름과 부서 조합 선택
    ```sql
    SELECT DISTINCT name, department FROM employees;
    ```

> ### 쉬운 요약
1. DISTINCT는 "중복된 값을 제거하고 고유한 값을 선택하는 명령어"
    - 주로 SELECT 문에서 사용

2. 여러 열에서 고유한 값 선택 가능
    - 특정 열 또는 여러 열의 고유한 값을 선택할 수 있음

> ### 비유
1. 서점에서 고유한 저자 찾기
    - DISTINCT는 서점에서 "고유한 저자 이름"을 찾는 작업
    - 예: SELECT DISTINCT author FROM books;

2. 음식점에서 고유한 메뉴 카테고리 선택
    - 데이터베이스가 음식점 메뉴라면, DISTINCT는 메뉴판에서 "고유한 카테고리"를 선택하는 작업
    - 예: SELECT DISTINCT category FROM menu;

[뒤로](mysql.md)
