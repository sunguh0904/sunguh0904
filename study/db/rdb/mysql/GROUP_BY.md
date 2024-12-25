## GROUP BY
> ### GROUP BY란?
GROUP BY는 데이터베이스에서 데이터를 특정 열을 기준으로 그룹화하여 집계 함수와 함께 사용되는 명령어. 주로 SELECT 문에서 사용

> ### GROUP BY의 예
1. 특정 열을 기준으로 그룹화
- 부서별로 직원 수를 계산
    ```sql
    SELECT department, COUNT(*) as employee_count
    FROM employees
    GROUP BY department;
    ```

2. 여러 열을 기준으로 그룹화
- 부서와 직책별로 평균 급여를 계산
    ```sql
    SELECT department, job_title, AVG(salary) as average_salary
    FROM employees
    GROUP BY department, job_title;
    ```

> ### 코드로 보기
1. 기본 GROUP BY 문
- 부서별로 총 급여를 계산
    ```sql
    SELECT department, SUM(salary) as total_salary
    FROM employees
    GROUP BY department;
    ```

2. 여러 열을 사용한 GROUP BY 문
- 부서와 직책별로 최대 급여를 계산
    ```sql
    SELECT department, job_title, MAX(salary) as max_salary
    FROM employees
    GROUP BY department, job_title;
    ```

> ### 쉬운 요약
1. GROUP BY는 "데이터를 특정 열을 기준으로 그룹화하는 명령어"
    - 주로 집계 함수와 함께 사용

2. 여러 열을 기준으로 그룹화 가능
    - 특정 열 또는 여러 열을 기준으로 데이터를 그룹화할 수 있음

> ### 비유
1. 서점에서 책을 장르별로 그룹화
    - GROUP BY는 서점에서 "책을 장르별로 그룹화하여 각 장르별 책 수를 계산하는 작업"
    - 예: SELECT genre, COUNT(*) as book_count FROM books GROUP BY genre;

2. 음식점에서 메뉴를 카테고리별로 그룹화
    - 데이터베이스가 음식점 메뉴라면, GROUP BY는 메뉴판에서 "메뉴를 카테고리별로 그룹화하여 각 카테고리별 메뉴 수를 계산하는 작업"
    - 예: SELECT category, COUNT(*) as menu_count FROM menu GROUP BY category;

[뒤로](mysql.md)
