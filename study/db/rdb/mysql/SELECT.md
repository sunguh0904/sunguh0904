## SELECT
> ### SELECT이란?
SELECT는 데이터베이스에서 "필요한 정보를 꺼내는 명령어"</br>
비유하자면, "서점에서 원하는 책을 고르는 작업"과 같음</br>
책이 많은 서점에서 원하는 책을 찾으려면, 책의 제목, 저자, 카테고리 등 조건을 기준으로 선택</br>
SELECT도 데이터베이스에서 특정 조건에 맞는 데이터를 선택하는 데 사용

> ### SELECT의 예
1. 모든 데이터를 선택
- 테이블에 있는 모든 데이터를 가져옴
    ```sql
    SELECT * FROM books;
    ```

2. 특정 열만 선택
- 테이블에서 특정 열만 가져옴
    ```sql
    SELECT title, author FROM books;
    ```

3. 조건에 맞는 데이터 선택
- 조건에 맞는 데이터만 가져옴
    ```sql
    SELECT * FROM books WHERE category = 'Fiction';
    ```

4. 데이터를 정렬
- 데이터를 특정 순서로 정렬하여 가져옴
    ```sql
    SELECT * FROM books ORDER BY title ASC;
    ```

> ### 코드로 보기
1. 기본 SELECT 문
- 모든 직원 데이터를 가져옴
    ```sql
    SELECT * FROM employees;
    ```

2. 조건문 사용
- 급여가 5000 이상인 직원의 이름과 급여만 가져옴
    ```sql
    SELECT name, salary FROM employees WHERE salary > 5000;
    ```

3. 데이터 정렬
- 급여가 높은 순으로 직원 정보를 가져옴
    ```sql
    SELECT name, salary FROM employees ORDER BY salary DESC;
    ```

> ### 쉬운 요약
1. SELECT는 "데이터를 꺼내오는 명령어"
    - 데이터베이스에 저장된 정보를 검색할 때 사용

2. 필요한 데이터만 선택 가능
    - 전체 데이터 또는 특정 조건에 맞는 데이터를 가져옴

3. 정렬, 필터링 드 다양한 기능 제공
    - 데이터를 원하는 순서나 조건에 맞게 출력할 수 있음

> ### 비유
1. 서점에서 책 찾기
    - SELECT는 서점에서 "특정 장르의 책"이나 "저자 이름이 같은 책"을 고르는 작업
    - 예: SELECT * FROM books WHERE author = '홍길동';

2. 음식점에서 메뉴 선택
    - 데이터베이스가 음식점 메뉴라면, SELECT는 메뉴판에서 원하는 음식을 선택하는 작업
    - 예: SELECT * FROM menu WHERE category = '음료';

[뒤로](mysql.md)