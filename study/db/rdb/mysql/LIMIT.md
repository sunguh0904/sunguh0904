## LIMIT
> ### LIMIT란?
LIMIT는 데이터베이스에서 쿼리 결과의 행 수를 제한하는 데 사용되는 명령어</br>
주로 SELECT 문에서 사용

> ### LIMIT의 예
1. 상위 N개의 행 선택
- 직원 테이블에서 상위 5명의 직원 선택
    ```sql
    SELECT * FROM employees LIMIT 5;
    ```

2. 특정 범위의 행 선택
- 직원 테이블에서 6번째부터 10번째까지의 직원 선택
    ```sql
    SELECT * FROM employees LIMIT 5 OFFSET 5;
    ```

> ### 코드로 보기
1. 기본 LIMIT 문
- 책 테이블에서 상위 3개의 책 선택
    ```sql
    SELECT * FROM books LIMIT 3;
    ```

2. OFFSET을 사용한 LIMIT 문
- 책 테이블에서 4번째부터 6번째까지의 책 선택
    ```sql
    SELECT * FROM books LIMIT 3 OFFSET 3;
    ```

> ### 쉬운 요약
1. LIMIT는 "쿼리 결과의 행 수를 제한하는 명령어"
    - 주로 SELECT 문에서 사용

2. OFFSET과 함께 사용 가능
    - 특정 범위의 행을 선택할 때 OFFSET을 함께 사용하여 시작 위치를 지정할 수 있음

> ### 비유
1. 서점에서 상위 N개의 책 선택
    - LIMIT는 서점에서 "상위 5개의 베스트셀러 책"을 선택하는 작업
    - 예: SELECT * FROM books LIMIT 5;

2. 음식점에서 특정 범위의 메뉴 선택
    - 데이터베이스가 음식점 메뉴라면, LIMIT는 메뉴판에서 "상위 3개의 인기 메뉴"를 선택하는 작업
    - 예: SELECT * FROM menu LIMIT 3;

[뒤로](mysql.md)
