## GROUP BY
> ### GROUP BY란?
GROUP BY는 데이터베이스에서 데이터를 그룹화하는 데 사용되는 절</br>
주로 집계 함수와 함께 사용

> ### GROUP BY의 종류
1. 특정 열을 기준으로 데이터 그룹화
    ```sql
    SELECT department, COUNT(*) FROM employees GROUP BY department;
    ```

2. 여러 열을 기준으로 데이터 그룹화
    ```sql
    SELECT department, job_title, COUNT(*) FROM employees GROUP BY department, job_title;
    ```

> ### 왜 사용해야 하는가?
1. **데이터 그룹화**: GROUP BY를 사용하면 데이터를 특정 기준으로 그룹화할 수 있음
2. **데이터 분석**: GROUP BY를 사용하여 데이터를 그룹화하고 집계하여 분석할 수 있음

> ### 쉬운 요약
1. GROUP BY는 "데이터를 그룹화하는 절"
    - 주로 집계 함수와 함께 사용

2. 여러 열을 기준으로 데이터 그룹화 가능
    - 특정 열 또는 여러 열을 기준으로 데이터를 그룹화할 수 있음

> ### 비유
1. 서점에서 책을 장르별로 그룹화
    - GROUP BY는 서점에서 "책을 장르별로 그룹화"하는 작업
    - 예: SELECT genre, COUNT(*) FROM books GROUP BY genre;

2. 음식점에서 메뉴를 카테고리별로 그룹화
    - GROUP BY는 메뉴판에서 "메뉴를 카테고리별로 그룹화"하는 작업
    - 예: SELECT category, COUNT(*) FROM menu GROUP BY category;

[뒤로](mysql.md)
