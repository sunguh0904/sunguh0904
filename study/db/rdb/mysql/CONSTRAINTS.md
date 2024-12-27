## CONSTRAINTS
> ### CONSTRAINTS란?
CONSTRAINTS는 데이터베이스에서 데이터의 무결성을 보장하기 위해 사용되는 제약 조건</br>
주로 테이블을 생성하거나 수정할 때 사용

> ### CONSTRAINTS의 주요 기능
1. PRIMARY KEY: 테이블의 각 행을 고유하게 식별
    ```sql
    -- id 열을 PRIMARY KEY로 설정하여 고유하게 식별
    CREATE TABLE employees (
        id INT PRIMARY KEY,
        name VARCHAR(100),
        position VARCHAR(100)
    );
    ```

2. FOREIGN KEY: 다른 테이블의 PRIMARY KEY를 참조하여 관계를 설정
    ```sql
    -- department_id 열을 FOREIGN KEY로 설정하여 departments 테이블의 id를 참조
    CREATE TABLE employees (
        id INT PRIMARY KEY,
        name VARCHAR(100),
        position VARCHAR(100),
        department_id INT,
        FOREIGN KEY (department_id) REFERENCES departments(id)
    );
    ```

3. UNIQUE: 열의 값이 고유하도록 설정
    ```sql
    -- email 열을 UNIQUE로 설정하여 중복된 값을 허용하지 않음
    CREATE TABLE employees (
        id INT PRIMARY KEY,
        name VARCHAR(100),
        email VARCHAR(100) UNIQUE
    );
    ```

4. CHECK: 열의 값이 특정 조건을 만족하도록 설정
    ```sql
    -- salary 열의 값이 0 이상이 되도록 설정
    CREATE TABLE employees (
        id INT PRIMARY KEY,
        name VARCHAR(100),
        salary INT,
        CHECK (salary >= 0)
    );
    ```

5. NOT NULL: 열의 값이 NULL이 될 수 없도록 설정
    ```sql
    -- name 열의 값이 NULL이 될 수 없도록 설정
    CREATE TABLE employees (
        id INT PRIMARY KEY,
        name VARCHAR(100) NOT NULL,
        position VARCHAR(100)
    );
    ```

> ### 왜 사용해야 하는가?
1. **데이터 무결성 보장**: CONSTRAINTS를 사용하면 데이터의 무결성을 보장할 수 있음
2. **데이터 관계 설정**: FOREIGN KEY를 사용하여 테이블 간의 관계를 설정할 수 있음
3. **데이터 유효성 검사**: CHECK, UNIQUE, NOT NULL 등을 사용하여 데이터의 유효성을 검사할 수 있음

> ### 쉬운 요약
1. CONSTRAINTS는 "데이터의 무결성을 보장하기 위해 사용되는 제약 조건"
    - 주로 테이블을 생성하거나 수정할 때 사용

2. PRIMARY KEY, FOREIGN KEY, UNIQUE, CHECK, NOT NULL 등의 제약 조건 제공
    - 데이터의 무결성을 보장하고 유효성을 검사할 수 있음

> ### 비유
1. 도서관에서 책 관리
    - CONSTRAINTS는 도서관에서 "책의 고유 번호를 설정하고, 특정 조건을 만족하도록 관리"하는 작업
    - 예: 책의 고유 번호를 설정하거나, 책의 상태를 검사

2. 음식점에서 메뉴 관리
    - CONSTRAINTS는 음식점에서 "메뉴의 고유 번호를 설정하고, 특정 조건을 만족하도록 관리"하는 작업
    - 예: 메뉴의 고유 번호를 설정하거나, 메뉴의 가격을 검사

[뒤로](mysql.md)
