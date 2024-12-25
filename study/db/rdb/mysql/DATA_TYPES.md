## DATA TYPES
> ### DATA TYPES란?
DATA TYPES는 데이터베이스에서 저장되는 데이터의 종류를 정의하는 데 사용되는 속성</br>
주로 숫자형, 문자열형, 날짜 및 시간형, 논리형 등이 있음

> ### DATA TYPES의 종류
1. 숫자형(Numeric Types): 정수, 부동 소수점 등을 포함
    - INT: 정수형 데이터 타입
        ```sql
        CREATE TABLE example (
            id INT,
            value INT
        );
        ```
    - DECIMAL: 고정 소수점 데이터 타입
        ```sql
        CREATE TABLE example (
            id INT,
            price DECIMAL(10, 2)
        );
        ```

2. 문자열형(String Types): 문자와 문자열 데이터를 포함
    - VARCHAR: 가변 길이 문자열 데이터 타입
        ```sql
        CREATE TABLE example (
            id INT,
            name VARCHAR(100)
        );
        ```
    - TEXT: 긴 문자열 데이터 타입
        ```sql
        CREATE TABLE example (
            id INT,
            description TEXT
        );
        ```

3. 날짜 및 시간형(Date and Time Types): 날짜와 시간 데이터를 포함
    - DATE: 날짜 데이터 타입
        ```sql
        CREATE TABLE example (
            id INT,
            created_date DATE
        );
        ```
    - TIMESTAMP: 날짜와 시간 데이터 타입
        ```sql
        CREATE TABLE example (
            id INT,
            created_at TIMESTAMP
        );
        ```

4. 논리형(Boolean Types): 참과 거짓 값을 포함
    - BOOLEAN: 논리형 데이터 타입
        ```sql
        CREATE TABLE example (
            id INT,
            is_active BOOLEAN
        );
        ```

> ### 왜 사용해야 하는가?
1. **데이터 저장 형식 정의**: DATA TYPES를 사용하면 데이터베이스에서 저장되는 데이터의 형식을 정의할 수 있음
2. **데이터 무결성 유지**: 데이터의 형식과 제약 조건을 정의하여 데이터 무결성을 유지할 수 있음
3. **효율적인 데이터 관리**: 데이터의 저장 형식을 정의하여 효율적으로 데이터를 관리할 수 있음

> ### 쉬운 요약
1. DATA TYPES는 "데이터베이스에서 저장되는 데이터의 종류를 정의하는 속성"
    - 주로 숫자형, 문자열형, 날짜 및 시간형, 논리형 등이 있음

2. 데이터의 저장 형식과 제약 조건을 정의하는 데 사용

> ### 비유
1. 서류 양식
    - DATA TYPES는 서류 양식에서 "각 칸에 입력할 데이터의 종류를 정의하는 것"과 같음
    - 예: 이름 칸은 문자열, 나이 칸은 숫자

2. 소프트웨어 변수 타입
    - DATA TYPES는 소프트웨어에서 "변수의 데이터 타입을 정의하는 것"과 같음
    - 예: 정수형 변수, 문자열 변수

[뒤로](mysql.md)
