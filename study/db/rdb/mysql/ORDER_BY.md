## ORDER BY
> ### ORDER BY란?
ORDER BY는 데이터베이스에서 결과를 정렬하는 데 사용되는 명령어</br>
특정 열을 기준으로 오름차순(ASC) 또는 내림차순(DESC)으로 정렬할 수 있음

> ### ORDER BY의 예
1. 오름차순 정렬
- 이름을 기준으로 오름차순으로 정렬
    ```sql
    SELECT * FROM employees ORDER BY name ASC;
    ```

2. 내림차순 정렬
- 급여를 기준으로 내림차순으로 정렬
    ```sql
    SELECT * FROM employees ORDER BY salary DESC;
    ```

> ### 코드로 보기
1. 기본 ORDER BY 문
- 이름을 기준으로 오름차순으로 직원 데이터를 정렬
    ```sql
    SELECT * FROM employees ORDER BY name ASC;
    ```

2. 여러 열을 기준으로 정렬
- 부서와 급여를 기준으로 정렬
    ```sql
    SELECT * FROM employees ORDER BY department ASC, salary DESC;
    ```

> ### 쉬운 요약
1. ORDER BY는 "데이터를 정렬하는 명령어"
    - 데이터를 특정 열을 기준으로 오름차순 또는 내림차순으로 정렬

2. 여러 열을 기준으로 정렬 가능
    - 여러 열을 기준으로 복합 정렬 가능

> ### 비유
1. 도서관에서 책 정렬하기
    - ORDER BY는 도서관에서 책을 "제목 순"이나 "저자 순"으로 정렬하는 작업
    - 예: SELECT * FROM books ORDER BY title ASC;

2. 음식점에서 메뉴 정렬
    - 데이터베이스가 음식점 메뉴라면, ORDER BY는 메뉴판을 "가격 순"이나 "인기 순"으로 정렬하는 작업
    - 예: SELECT * FROM menu ORDER BY price DESC;

[뒤로](mysql.md)