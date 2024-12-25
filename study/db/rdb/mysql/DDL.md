## DDL
> ### DDL 이란?
DDL(Data Definition Language)은 데이터베이스의 구조를 정의하고 관리하는 데 사용되는 언어</br>
주로 CREATE, ALTER, DROP, TRUNCATE 등이 있음

> ### DDL의 종류
1. CREATE: 새로운 데이터베이스 객체(테이블, 인덱스 등)를 생성
    ```sql
    CREATE TABLE employees (
        id INT PRIMARY KEY,
        name VARCHAR(100),
        position VARCHAR(100)
    );
    ```

2. ALTER: 기존 데이터베이스 객체의 구조를 변경
    ```sql
    ALTER TABLE employees ADD COLUMN salary INT;
    ```

3. DROP: 기존 데이터베이스 객체를 삭제
    ```sql
    DROP TABLE employees;
    ```

4. TRUNCATE: 테이블의 모든 데이터를 삭제하지만 구조는 유지
    ```sql
    TRUNCATE TABLE employees;
    ```

> ### 코드로 보기
1. CREATE 사용
- 새로운 테이블 생성
    ```sql
    CREATE TABLE departments (
        id INT PRIMARY KEY,
        name VARCHAR(100)
    );
    ```

2. ALTER 사용
- 테이블에 새로운 열 추가
    ```sql
    ALTER TABLE departments ADD COLUMN location VARCHAR(100);
    ```

3. DROP 사용
- 테이블 삭제
    ```sql
    DROP TABLE departments;
    ```

4. TRUNCATE 사용
- 테이블의 모든 데이터 삭제
    ```sql
    TRUNCATE TABLE departments;
    ```

> ### 쉬운 요약
1. DDL은 "데이터베이스의 구조를 정의하고 관리하는 언어"
    - 주로 CREATE, ALTER, DROP, TRUNCATE 등이 있음

2. 데이터베이스 객체의 생성, 변경, 삭제, 초기화에 사용

> ### 비유
1. 건물 설계와 건축
    - DDL은 건물 설계와 건축에서 "건물의 구조를 정의하고 변경하는 작업"과 같음
    - 예: 새로운 방을 추가하거나, 기존 방을 제거

2. 소프트웨어 설치와 설정
    - DDL은 소프트웨어 설치와 설정에서 "소프트웨어의 구조를 정의하고 관리하는 작업"과 같음
    - 예: 새로운 기능을 추가하거나, 기존 기능을 제거

[뒤로](mysql.md)
