## LIMIT
> ### LIMIT란?
LIMIT는 데이터베이스에서 조회할 데이터의 개수를 제한하는 데 사용되는 절</br>
주로 SELECT 문에서 사용

> ### LIMIT의 주요 기능
1. 조회할 데이터의 개수 제한: 최대 조회할 데이터의 개수를 지정
    ```sql
    -- 최대 10개의 데이터를 조회
    SELECT * FROM employees LIMIT 10;
    ```

2. 특정 위치부터 조회할 데이터의 개수 제한: OFFSET을 사용하여 특정 위치에서부터 데이터를 조회
    ```sql
    -- 10번째 데이터부터 최대 5개의 데이터를 조회
    SELECT * FROM employees LIMIT 5 OFFSET 10;
    ```

> ### 왜 사용해야 하는가?
1. **데이터 조회 제한**: LIMIT를 사용하면 조회할 데이터의 개수를 제한할 수 있음
2. **페이징 처리**: LIMIT와 OFFSET을 사용하여 데이터를 페이지 단위로 나누어 조회할 수 있음

> ### 쉬운 요약
1. LIMIT는 "조회할 데이터의 개수를 제한하는 절"
    - 주로 SELECT 문에서 사용

2. OFFSET과 함께 사용 가능
    - OFFSET을 사용하여 특정 위치부터 데이터를 조회할 수 있음

> ### 비유
1. 서점에서 책 목록 제한
    - LIMIT는 서점에서 "책 목록을 최대 10권만 조회"하는 작업
    - 예: SELECT * FROM books LIMIT 10;

2. 음식점에서 메뉴 목록 제한
    - LIMIT는 메뉴판에서 "메뉴 목록을 최대 5개만 조회"하는 작업
    - 예: SELECT * FROM menu LIMIT 5;

[뒤로](mysql.md)
