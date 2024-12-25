## 논리 연산자
> ### 논리 연산자란?
논리 연산자는 데이터베이스에서 WHERE 절의 여러 조건을 결합하는 데 사용되는 연산자</br>
여러 기준에 따라 데이터를 필터링하는 데 도움

> ### 논리 연산자의 종류
1. `AND`: 여러 조건을 결합하여 모든 조건이 참일 때 참을 반환
    ```sql
    SELECT * FROM employees WHERE age >= 30 AND department = 'HR';
    ```

2. `OR`: 여러 조건을 결합하여 조건 중 하나라도 참일 때 참을 반환
    ```sql
    SELECT * FROM employees WHERE age >= 30 OR department = 'HR';
    ```

3. `NOT`: 조건을 부정
    ```sql
    SELECT * FROM employees WHERE NOT age >= 30;
    ```

> ### 코드로 보기
1. AND 연산자 사용
- 나이가 30 이상이고 HR 부서에 속한 직원 선택
    ```sql
    SELECT * FROM employees WHERE age >= 30 AND department = 'HR';
    ```

2. OR 연산자 사용
- 나이가 30 이상이거나 HR 부서에 속한 직원 선택
    ```sql
    SELECT * FROM employees WHERE age >= 30 OR department = 'HR';
    ```

3. NOT 연산자 사용
- 나이가 30 이상이 아닌 직원 선택
    ```sql
    SELECT * FROM employees WHERE NOT age >= 30;
    ```

> ### 쉬운 요약
1. 논리 연산자는 "여러 조건을 결합하는 연산자"
    - 주로 WHERE 절에서 여러 기준에 따라 데이터를 필터링할 때 사용

2. 다양한 논리 연산자 제공
    - `AND`, `OR`, `NOT` 등의 연산자를 사용하여 복잡한 조건을 지정할 수 있음

> ### 비유
1. 서점에서 책 찾기
    - 논리 연산자는 서점에서 "가격이 10000원 이상이고 2020년 이후에 출판된 책" 또는 "가격이 10000원 이상이거나 2020년 이후에 출판된 책"을 찾는 작업
    - 예: SELECT * FROM books WHERE price >= 10000 AND publish_year > 2020;

2. 음식점에서 메뉴 선택
    - 데이터베이스가 음식점 메뉴라면, 논리 연산자는 메뉴판에서 "칼로리가 500 이하이고 채식주의자인 음식" 또는 "칼로리가 500 이하이거나 채식주의자인 음식"을 선택하는 작업
    - 예: SELECT * FROM menu WHERE calories <= 500 AND is_vegetarian = true;

[뒤로](mysql.md)
