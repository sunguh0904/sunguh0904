## IN
> ### IN이란?
IN은 데이터베이스에서 특정 값 목록 중 하나와 일치하는 데이터를 선택하는 데 사용되는 연산자</br>
주로 WHERE 절에서 사용

> ### IN의 예
1. 특정 값 목록에 있는 데이터 선택
- 부서가 'HR', 'Engineering', 'Marketing' 중 하나인 직원 선택
    ```sql
    SELECT * FROM employees WHERE department IN ('HR', 'Engineering', 'Marketing');
    ```

2. 숫자 목록에 있는 데이터 선택
- 나이가 25, 30, 35 중 하나인 직원 선택
    ```sql
    SELECT * FROM employees WHERE age IN (25, 30, 35);
    ```

> ### 코드로 보기
1. 기본 IN 문
- 부서가 'HR' 또는 'Engineering'인 직원 선택
    ```sql
    SELECT * FROM employees WHERE department IN ('HR', 'Engineering');
    ```

2. 숫자 목록을 사용한 IN 문
- 나이가 20, 25, 30 중 하나인 직원 선택
    ```sql
    SELECT * FROM employees WHERE age IN (20, 25, 30);
    ```

> ### 쉬운 요약
1. IN은 "특정 값 목록 중 하나와 일치하는 데이터를 선택하는 연산자"
    - 주로 WHERE 절에서 사용

2. 여러 값을 한 번에 비교 가능
    - 특정 값 목록을 지정하여 데이터를 필터링할 수 있음

> ### 비유
1. 서점에서 특정 저자의 책 찾기
    - IN은 서점에서 "저자가 '홍길동', '이순신', '김유신' 중 하나인 책"을 찾는 작업
    - 예: SELECT * FROM books WHERE author IN ('홍길동', '이순신', '김유신');

2. 음식점에서 특정 메뉴 선택
    - 데이터베이스가 음식점 메뉴라면, IN은 메뉴판에서 "카테고리가 '음료', '디저트', '메인 요리' 중 하나인 음식"을 선택하는 작업
    - 예: SELECT * FROM menu WHERE category IN ('음료', '디저트', '메인 요리');

[뒤로](mysql.md)
