## ORDER BY
> ### ORDER BY란?
ORDER BY는 데이터베이스에서 데이터를 정렬하는 데 사용되는 절</br>
주로 SELECT 문에서 사용

> ### ORDER BY의 주요 기능
1. 오름차순 정렬: 데이터를 오름차순으로 정렬
    ```sql
    -- name 열을 기준으로 오름차순 정렬
    SELECT * FROM employees ORDER BY name ASC;
    ```

2. 내림차순 정렬: 데이터를 내림차순으로 정렬
    ```sql
    -- name 열을 기준으로 내림차순 정렬
    SELECT * FROM employees ORDER BY name DESC;
    ```

> ### 왜 사용해야 하는가?
1. **데이터 정렬**: ORDER BY를 사용하면 데이터를 원하는 순서로 정렬할 수 있음
2. **가독성 향상**: 데이터를 정렬하여 가독성을 향상시킬 수 있음

> ### 쉬운 요약
1. ORDER BY는 "데이터를 정렬하는 절"
    - 주로 SELECT 문에서 사용

2. 오름차순, 내림차순 정렬 가능
    - 데이터를 오름차순 또는 내림차순으로 정렬할 수 있음

> ### 비유
1. 서점에서 책을 저자 이름 순으로 정렬
    - ORDER BY는 서점에서 "책을 저자 이름 순으로 정렬"하는 작업
    - 예: SELECT * FROM books ORDER BY author ASC;

2. 음식점에서 메뉴를 가격 순으로 정렬
    - ORDER BY는 메뉴판에서 "메뉴를 가격 순으로 정렬"하는 작업
    - 예: SELECT * FROM menu ORDER BY price DESC;

[뒤로](mysql.md)