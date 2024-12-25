## INDEX
> ### INDEX란?
INDEX는 데이터베이스 테이블에서 데이터를 빠르게 조회할 수 있도록 도와주는 데이터 구조</br>
주로 검색 성능을 향상시키기 위해 사용됨

> ### INDEX의 종류
1. 기본 인덱스(Primary Index): 테이블의 PRIMARY KEY에 자동으로 생성되는 인덱스
    ```sql
    CREATE TABLE employees (
        id INT PRIMARY KEY,
        name VARCHAR(100)
    );
    ```

2. 고유 인덱스(Unique Index): 열의 모든 값이 고유하도록 설정하는 인덱스
    ```sql
    CREATE UNIQUE INDEX idx_unique_email ON users(email);
    ```

3. 일반 인덱스(Non-Unique Index): 중복된 값을 허용하는 인덱스
    ```sql
    CREATE INDEX idx_name ON employees(name);
    ```

4. 복합 인덱스(Composite Index): 여러 열을 결합하여 생성하는 인덱스
    ```sql
    CREATE INDEX idx_name_position ON employees(name, position);
    ```

> ### 왜 사용해야 하는가?
1. **검색 성능 향상**: 인덱스를 사용하면 데이터를 빠르게 조회할 수 있어 검색 성능이 향상됨
2. **데이터 정렬**: 인덱스를 사용하면 데이터를 정렬된 상태로 유지할 수 있음
3. **데이터 무결성**: 고유 인덱스를 사용하면 데이터의 고유성을 보장할 수 있음

> ### 쉬운 요약
1. INDEX는 "데이터베이스 테이블에서 데이터를 빠르게 조회할 수 있도록 도와주는 데이터 구조"
    - 주로 검색 성능을 향상시키기 위해 사용됨

2. 기본 인덱스, 고유 인덱스, 일반 인덱스, 복합 인덱스 등이 있음

> ### 비유
1. 책의 목차
    - INDEX는 책에서 "목차"와 같음
    - 예: 목차를 통해 원하는 내용을 빠르게 찾을 수 있음

2. 도서관의 분류 시스템
    - INDEX는 도서관에서 "책을 분류하는 시스템"과 같음
    - 예: 분류 시스템을 통해 원하는 책을 빠르게 찾을 수 있음

[뒤로](mysql.md)
