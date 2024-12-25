## 비교 연산자
> ### 비교 연산자란?
비교 연산자는 데이터베이스에서 두 값을 비교하는 데 사용되는 연산자</br>
주로 WHERE 절에서 조건을 지정할 때 사용

> ### 비교 연산자의 종류
1. `=`: 두 값이 같은지 비교
    ```sql
    SELECT * FROM employees WHERE age = 30;
    ```

2. `!=` 또는 `<>`: 두 값이 다른지 비교
    ```sql
    SELECT * FROM employees WHERE age != 30;
    ```

3. `>`: 왼쪽 값이 오른쪽 값보다 큰지 비교
    ```sql
    SELECT * FROM employees WHERE salary > 5000;
    ```

4. `<`: 왼쪽 값이 오른쪽 값보다 작은지 비교
    ```sql
    SELECT * FROM employees WHERE salary < 5000;
    ```

5. `>=`: 왼쪽 값이 오른쪽 값보다 크거나 같은지 비교
    ```sql
    SELECT * FROM employees WHERE age >= 30;
    ```

6. `<=`: 왼쪽 값이 오른쪽 값보다 작거나 같은지 비교
    ```sql
    SELECT * FROM employees WHERE age <= 30;
    ```

> ### 코드로 보기
1. 기본 비교 연산자 사용
- 나이가 30인 직원 선택
    ```sql
    SELECT * FROM employees WHERE age = 30;
    ```

2. 여러 비교 연산자 사용
- 급여가 5000 이상이고 나이가 30 이하인 직원 선택
    ```sql
    SELECT * FROM employees WHERE salary >= 5000 AND age <= 30;
    ```

> ### 쉬운 요약
1. 비교 연산자는 "두 값을 비교하는 연산자"
    - 주로 WHERE 절에서 조건을 지정할 때 사용

2. 다양한 비교 연산자 제공
    - `=`, `!=`, `>`, `<`, `>=`, `<=` 등의 연산자를 사용하여 조건을 지정할 수 있음

> ### 비유
1. 서점에서 책 비교하기
    - 비교 연산자는 서점에서 "가격이 10000원 이상인 책"이나 "출판 연도가 2020년 이후인 책"을 찾는 작업
    - 예: SELECT * FROM books WHERE price >= 10000;

2. 음식점에서 메뉴 비교하기
    - 데이터베이스가 음식점 메뉴라면, 비교 연산자는 메뉴판에서 "칼로리가 500 이하인 음식"을 선택하는 작업
    - 예: SELECT * FROM menu WHERE calories <= 500;

[뒤로](mysql.md)
