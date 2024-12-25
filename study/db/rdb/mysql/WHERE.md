## WHERE
> ### WHERE란?
WHERE는 데이터베이스에서 특정 조건에 맞는 데이터를 선택하는 데 사용되는 명령어</br>
조건을 지정하여 원하는 데이터만 필터링할 수 있음

> ### WHERE의 예
1. 특정 조건에 맞는 데이터 선택
- 나이가 30 이상인 직원 선택
    ```sql
    SELECT * FROM employees WHERE age >= 30;
    ```

2. 여러 조건을 사용한 데이터 선택
- 나이가 30 이상이고 부서가 'HR'인 직원 선택
    ```sql
    SELECT * FROM employees WHERE age >= 30 AND department = 'HR';
    ```

> ### 코드로 보기
1. 기본 WHERE 문
- 급여가 5000 이상인 직원 선택
    ```sql
    SELECT * FROM employees WHERE salary >= 5000;
    ```

2. 여러 조건을 사용한 WHERE 문
- 급여가 5000 이상이고 부서가 'Engineering'인 직원 선택
    ```sql
    SELECT * FROM employees WHERE salary >= 5000 AND department = 'Engineering';
    ```

> ### 쉬운 요약
1. WHERE는 "조건에 맞는 데이터를 선택하는 명령어"
    - 특정 조건에 맞는 데이터를 필터링할 때 사용

2. 여러 조건을 조합하여 사용 가능
    - AND, OR 등의 논리 연산자를 사용하여 복합 조건을 지정할 수 있음

> ### 비유
1. 서점에서 특정 조건에 맞는 책 찾기
    - WHERE는 서점에서 "특정 저자의 책"이나 "특정 장르의 책"을 찾는 작업
    - 예: SELECT * FROM books WHERE author = '홍길동';

2. 음식점에서 특정 조건에 맞는 메뉴 선택
    - 데이터베이스가 음식점 메뉴라면, WHERE는 메뉴판에서 "가격이 10000원 이하인 음식"을 선택하는 작업
    - 예: SELECT * FROM menu WHERE price <= 10000;

[뒤로](mysql.md)
