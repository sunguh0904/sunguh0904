## LIKE
> ### LIKE란?
LIKE는 데이터베이스에서 특정 패턴과 일치하는 데이터를 검색하는 데 사용되는 연산자</br>
주로 와일드카드 문자(%, _)와 함께 사용

> ### LIKE의 예
1. 특정 패턴과 일치하는 데이터 선택
- 이름이 'John'으로 시작하는 직원 선택
    ```sql
    SELECT * FROM employees WHERE name LIKE 'John%';
    ```

2. 특정 패턴을 포함하는 데이터 선택
- 이름에 'ohn'이 포함된 직원 선택
    ```sql
    SELECT * FROM employees WHERE name LIKE '%ohn%';
    ```

> ### 코드로 보기
1. 기본 LIKE 문
- 이메일이 'gmail.com'으로 끝나는 직원 선택
    ```sql
    SELECT * FROM employees WHERE email LIKE '%@gmail.com';
    ```

2. 와일드카드 사용
- 이름이 'J'로 시작하고 'n'으로 끝나는 직원 선택
    ```sql
    SELECT * FROM employees WHERE name LIKE 'J%n';
    ```

> ### 쉬운 요약
1. LIKE는 "특정 패턴과 일치하는 데이터를 검색하는 연산자"
    - 와일드카드 문자(%, _)를 사용하여 패턴을 지정할 수 있음

2. 다양한 패턴 매칭 가능
    - 문자열의 시작, 끝, 포함 여부 등을 기준으로 데이터 검색 가능

> ### 비유
1. 서점에서 특정 패턴의 책 찾기
    - LIKE는 서점에서 "제목이 'Harry'로 시작하는 책"이나 "저자 이름에 'Rowling'이 포함된 책"을 찾는 작업
    - 예: SELECT * FROM books WHERE title LIKE 'Harry%';

2. 음식점에서 특정 패턴의 메뉴 선택
    - 데이터베이스가 음식점 메뉴라면, LIKE는 메뉴판에서 "이름에 '치즈'가 포함된 음식"을 선택하는 작업
    - 예: SELECT * FROM menu WHERE name LIKE '%치즈%';

[뒤로](mysql.md)
