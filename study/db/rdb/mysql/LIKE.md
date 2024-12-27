## LIKE
> ### LIKE란?
LIKE는 데이터베이스에서 특정 패턴과 일치하는 데이터를 선택하는 데 사용되는 연산자</br>
주로 WHERE 절에서 사용

> ### LIKE의 주요 기능
1. 특정 패턴과 일치하는 데이터 선택: 와일드카드 문자를 사용하여 패턴을 지정
    ```sql
    -- name이 'J'로 시작하는 데이터를 조회
    SELECT * FROM employees WHERE name LIKE 'J%';
    ```

2. 특정 패턴과 일치하지 않는 데이터 선택: NOT LIKE를 사용하여 패턴과 일치하지 않는 데이터를 조회
    ```sql
    -- name이 'J'로 시작하지 않는 데이터를 조회
    SELECT * FROM employees WHERE name NOT LIKE 'J%';
    ```

> ### 왜 사용해야 하는가?
1. **패턴 매칭**: LIKE를 사용하면 특정 패턴과 일치하는 데이터를 쉽게 조회할 수 있음
2. **데이터 필터링**: LIKE를 사용하여 데이터를 필터링하고 필요한 정보를 추출할 수 있음

> ### 쉬운 요약
1. LIKE는 "특정 패턴과 일치하는 데이터를 선택하는 연산자"
    - 주로 WHERE 절에서 사용

2. 와일드카드 문자 사용 가능
    - `%`와 `_` 와일드카드 문자를 사용하여 패턴을 지정할 수 있음

> ### 비유
1. 서점에서 특정 제목의 책 찾기
    - LIKE는 서점에서 "특정 제목의 책"을 찾는 작업
    - 예: SELECT * FROM books WHERE title LIKE 'Harry Potter%';

2. 음식점에서 특정 이름의 메뉴 선택
    - LIKE는 메뉴판에서 "특정 이름의 음식"을 선택하는 작업
    - 예: SELECT * FROM menu WHERE name LIKE 'Chicken%';

[뒤로](mysql.md)
