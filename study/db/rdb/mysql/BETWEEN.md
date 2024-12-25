## BETWEEN
> ### BETWEEN이란?
BETWEEN은 데이터베이스에서 두 값 사이의 범위에 있는 데이터를 선택하는 데 사용되는 연산자</br>
주로 WHERE 절에서 사용

> ### BETWEEN의 예
1. 특정 범위에 있는 데이터 선택
- 나이가 20에서 30 사이인 직원 선택
    ```sql
    SELECT * FROM employees WHERE age BETWEEN 20 AND 30;
    ```

2. 날짜 범위에 있는 데이터 선택
- 2021년 1월 1일부터 2021년 12월 31일 사이에 고용된 직원 선택
    ```sql
    SELECT * FROM employees WHERE hire_date BETWEEN '2021-01-01' AND '2021-12-31';
    ```

> ### 코드로 보기
1. 기본 BETWEEN 문
- 급여가 3000에서 5000 사이인 직원 선택
    ```sql
    SELECT * FROM employees WHERE salary BETWEEN 3000 AND 5000;
    ```

2. 날짜 범위를 사용한 BETWEEN 문
- 2020년 1월 1일부터 2020년 12월 31일 사이에 고용된 직원 선택
    ```sql
    SELECT * FROM employees WHERE hire_date BETWEEN '2020-01-01' AND '2020-12-31';
    ```

> ### 쉬운 요약
1. BETWEEN은 "두 값 사이의 범위에 있는 데이터를 선택하는 연산자"
    - 주로 WHERE 절에서 사용

2. 숫자, 날짜 등 다양한 데이터 타입에 사용 가능
    - 숫자, 날짜 등의 범위를 지정하여 데이터를 필터링할 수 있음

> ### 비유
1. 서점에서 특정 가격 범위의 책 찾기
    - BETWEEN은 서점에서 "가격이 10000원에서 20000원 사이인 책"을 찾는 작업
    - 예: SELECT * FROM books WHERE price BETWEEN 10000 AND 20000;

2. 음식점에서 특정 칼로리 범위의 메뉴 선택
    - 데이터베이스가 음식점 메뉴라면, BETWEEN은 메뉴판에서 "칼로리가 300에서 600 사이인 음식"을 선택하는 작업
    - 예: SELECT * FROM menu WHERE calories BETWEEN 300 AND 600;

[뒤로](mysql.md)
