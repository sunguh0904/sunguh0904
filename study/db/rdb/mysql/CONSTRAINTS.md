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

> ### 코드로 보기
1. PRIMARY KEY 사용
- 테이블의 각 행을 고유하게 식별
    ```sql
    CREATE TABLE departments (
        id INT PRIMARY KEY,
        name VARCHAR(100)
    );
    ```

2. FOREIGN KEY 사용
- 한 테이블의 열이 다른 테이블의 PRIMARY KEY를 참조
    ```sql
    CREATE TABLE projects (
        project_id INT PRIMARY KEY,
        department_id INT,
        FOREIGN KEY (department_id) REFERENCES departments(id)
    );
    ```

3. UNIQUE 사용
- 열의 모든 값이 고유하도록 설정
    ```sql
    CREATE TABLE accounts (
        account_id INT PRIMARY KEY,
        username VARCHAR(100) UNIQUE
    );
    ```

4. CHECK 사용
- 열의 값이 특정 조건을 만족하도록 설정
    ```sql
    CREATE TABLE inventory (
        item_id INT PRIMARY KEY,
        quantity INT,
        CHECK (quantity >= 0)
    );
    ```

5. DEFAULT 사용
- 열의 기본값을 설정
    ```sql
    CREATE TABLE memberships (
        membership_id INT PRIMARY KEY,
        start_date DATE DEFAULT CURRENT_DATE
    );
    ```

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
