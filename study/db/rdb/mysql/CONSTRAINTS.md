## CONSTRAINTS
> ### CONSTRAINTS란?
CONSTRAINTS는 데이터베이스 테이블의 데이터 무결성을 보장하기 위해 사용되는 규칙이나 제약 조건</br>
주로 PRIMARY KEY, FOREIGN KEY, UNIQUE, CHECK, DEFAULT 등이 있음

> ### CONSTRAINTS의 종류
1. PRIMARY KEY: 테이블의 각 행을 고유하게 식별하는 열 또는 열의 집합
    ```sql
    CREATE TABLE employees (
        id INT PRIMARY KEY,
        name VARCHAR(100)
    );
    ```

2. FOREIGN KEY: 한 테이블의 열이 다른 테이블의 PRIMARY KEY를 참조하도록 설정
    ```sql
    CREATE TABLE orders (
        order_id INT PRIMARY KEY,
        employee_id INT,
        FOREIGN KEY (employee_id) REFERENCES employees(id)
    );
    ```

3. UNIQUE: 열의 모든 값이 고유하도록 설정
    ```sql
    CREATE TABLE users (
        user_id INT PRIMARY KEY,
        email VARCHAR(100) UNIQUE
    );
    ```

4. CHECK: 열의 값이 특정 조건을 만족하도록 설정
    ```sql
    CREATE TABLE products (
        product_id INT PRIMARY KEY,
        price DECIMAL(10, 2),
        CHECK (price > 0)
    );
    ```

5. DEFAULT: 열의 기본값을 설정
    ```sql
    CREATE TABLE customers (
        customer_id INT PRIMARY KEY,
        created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
    );
    ```

> ### 왜 사용해야 하는가?
1. **데이터 무결성 보장**: CONSTRAINTS를 사용하면 데이터의 무결성을 보장할 수 있음
2. **데이터 고유성 유지**: PRIMARY KEY, UNIQUE 등을 사용하여 데이터의 고유성을 유지할 수 있음
3. **참조 무결성 유지**: FOREIGN KEY를 사용하여 테이블 간의 참조 무결성을 유지할 수 있음

> ### 쉬운 요약
1. CONSTRAINTS는 "데이터베이스 테이블의 데이터 무결성을 보장하는 규칙"
    - 주로 PRIMARY KEY, FOREIGN KEY, UNIQUE, CHECK, DEFAULT 등이 있음

2. 데이터의 고유성, 참조 무결성, 조건 만족, 기본값 설정 등에 사용

> ### 비유
1. 학교 규칙
    - CONSTRAINTS는 학교에서 "학생들이 따라야 할 규칙"과 같음
    - 예: 학생증 번호는 고유해야 함 (PRIMARY KEY)

2. 회사 정책
    - CONSTRAINTS는 회사에서 "직원들이 따라야 할 정책"과 같음
    - 예: 직원의 이메일 주소는 고유해야 함 (UNIQUE)

[뒤로](mysql.md)
