## DDL
> ### DDL이란?
DDL(Data Definition Language)은 데이터베이스의 구조를 정의하고 관리하는 데 사용되는 언어</br>
주로 CREATE, ALTER, DROP, TRUNCATE 등이 있음

> ### DDL의 주요 기능
1. CREATE: 새로운 데이터베이스 객체(테이블, 인덱스 등)를 생성
    ```sql
    -- employees 테이블을 생성
    CREATE TABLE employees (
        id INT PRIMARY KEY,
        name VARCHAR(100),
        position VARCHAR(100)
    );
    ```

2. ALTER: 기존 데이터베이스 객체의 구조를 변경
    ```sql
    -- employees 테이블에 salary 열을 추가
    ALTER TABLE employees ADD COLUMN salary INT;
    ```

3. DROP: 기존 데이터베이스 객체를 삭제
    ```sql
    -- employees 테이블을 삭제
    DROP TABLE employees;
    ```

4. TRUNCATE: 테이블의 모든 데이터를 삭제하지만 구조는 유지
    ```sql
    -- employees 테이블의 모든 데이터를 삭제
    TRUNCATE TABLE employees;
    ```

> ### 왜 사용해야 하는가?
1. **데이터베이스 구조 정의**: DDL을 사용하면 데이터베이스의 구조를 정의하고 관리할 수 있음
2. **데이터 무결성 유지**: 데이터베이스 객체의 생성, 변경, 삭제를 통해 데이터 무결성을 유지할 수 있음
3. **효율적인 데이터 관리**: 데이터베이스 구조를 효율적으로 관리하여 성능을 최적화할 수 있음

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
