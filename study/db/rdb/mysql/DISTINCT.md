## DISTINCT
> ### DISTINCT란?
DISTINCT는 데이터베이스에서 중복된 값을 제거하고 고유한 값을 선택하는 데 사용되는 연산자</br>
주로 SELECT 문에서 사용

> ### DISTINCT의 주요 기능
1. 중복된 값을 제거하고 고유한 값 선택: 특정 열의 고유한 값을 조회
    ```sql
    -- department 열에서 중복된 값을 제거하고 고유한 값을 조회
    SELECT DISTINCT department FROM employees;
    ```

2. 여러 열에서 고유한 값 선택: 여러 열의 조합에서 고유한 값을 조회
    ```sql
    -- department와 position 열의 조합에서 고유한 값을 조회
    SELECT DISTINCT department, position FROM employees;
    ```

> ### 왜 사용해야 하는가?
1. **중복 제거**: DISTINCT를 사용하면 중복된 값을 제거하고 고유한 값을 조회할 수 있음
2. **데이터 필터링**: DISTINCT를 사용하여 데이터를 필터링하고 필요한 정보를 추출할 수 있음

> ### 쉬운 요약
1. DISTINCT는 "중복된 값을 제거하고 고유한 값을 선택하는 연산자"
    - 주로 SELECT 문에서 사용

2. 여러 열에서 고유한 값 선택 가능
    - 여러 열의 조합에서 고유한 값을 조회할 수 있음

> ### 비유
1. 서점에서 고유한 저자의 책 찾기
    - DISTINCT는 서점에서 "고유한 저자의 책"을 찾는 작업
    - 예: SELECT DISTINCT author FROM books;

2. 음식점에서 고유한 재료가 포함된 메뉴 선택
    - DISTINCT는 메뉴판에서 "고유한 재료가 포함된 음식"을 선택하는 작업
    - 예: SELECT DISTINCT ingredient FROM menu;

[뒤로](mysql.md)
