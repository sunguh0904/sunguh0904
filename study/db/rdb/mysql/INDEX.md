## INDEX
> ### INDEX란?
INDEX는 데이터베이스에서 검색 성능을 향상시키기 위해 사용되는 데이터 구조</br>
주로 테이블의 특정 열에 대해 생성

> ### INDEX의 주요 기능
1. 기본 인덱스 생성: 특정 열에 대해 인덱스를 생성
    ```sql
    -- name 열에 대해 기본 인덱스를 생성
    CREATE INDEX idx_name ON employees(name);
    ```

2. 고유 인덱스 생성: 특정 열에 대해 중복을 허용하지 않는 인덱스를 생성
    ```sql
    -- name 열에 대해 고유 인덱스를 생성
    CREATE UNIQUE INDEX idx_unique_name ON employees(name);
    ```

> ### 왜 사용해야 하는가?
1. **검색 성능 향상**: INDEX를 사용하면 데이터베이스의 검색 성능을 향상시킬 수 있음
2. **데이터 정렬**: INDEX를 사용하여 데이터를 정렬하고 빠르게 접근할 수 있음

> ### 쉬운 요약
1. INDEX는 "검색 성능을 향상시키기 위해 사용되는 데이터 구조"
    - 주로 테이블의 특정 열에 대해 생성

2. 기본 인덱스, 고유 인덱스 등이 있음

> ### 비유
1. 도서관에서 책의 색인
    - INDEX는 도서관에서 "책의 색인"과 같음
    - 예: CREATE INDEX idx_title ON books(title);

2. 음식점에서 메뉴의 색인
    - INDEX는 메뉴판에서 "메뉴의 색인"과 같음
    - 예: CREATE INDEX idx_dish_name ON menu(dish_name);

[뒤로](mysql.md)
