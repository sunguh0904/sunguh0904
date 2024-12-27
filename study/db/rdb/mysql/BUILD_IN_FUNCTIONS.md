## BUILD-IN FUNCTIONS
> ### BUILD-IN FUNCTIONS란?
BUILD-IN FUNCTIONS는 데이터베이스에서 자주 사용되는 작업을 쉽게 수행할 수 있도록 미리 정의된 함수들</br>
주로 문자열 함수, 숫자 함수, 날짜 및 시간 함수, 논리 함수 등이 있음

> ### BUILD-IN FUNCTIONS의 주요 기능
1. 문자열 함수(String Functions): 문자열을 조작하거나 정보를 추출하는 데 사용
    - `CONCAT`: 두 개 이상의 문자열을 연결
        ```sql
        -- 'Hello'와 'World' 문자열을 연결
        SELECT CONCAT('Hello', ' ', 'World');
        ```
    - `SUBSTRING`: 문자열의 일부를 추출
        ```sql
        -- 'Hello World' 문자열에서 첫 5글자를 추출
        SELECT SUBSTRING('Hello World', 1, 5);
        ```
    - `LENGTH`: 문자열의 길이를 반환
        ```sql
        -- 'Hello World' 문자열의 길이를 반환
        SELECT LENGTH('Hello World');
        ```

2. 숫자 함수(Numeric Functions): 숫자 값을 계산하거나 변환하는 데 사용
    - `ABS`: 숫자의 절대값을 반환
        ```sql
        -- -10의 절대값을 반환
        SELECT ABS(-10);
        ```
    - `ROUND`: 숫자를 반올림
        ```sql
        -- 123.456을 소수점 둘째 자리에서 반올림
        SELECT ROUND(123.456, 2);
        ```
    - `CEIL`: 숫자를 올림
        ```sql
        -- 123.456을 올림하여 반환
        SELECT CEIL(123.456);
        ```

3. 날짜 및 시간 함수(Date and Time Functions): 날짜와 시간 값을 조작하거나 정보를 추출하는 데 사용
    - `NOW`: 현재 날짜와 시간을 반환
        ```sql
        -- 현재 날짜와 시간을 반환
        SELECT NOW();
        ```
    - `DATE_ADD`: 날짜에 특정 간격을 더함
        ```sql
        -- '2023-01-01'에 1일을 더함
        SELECT DATE_ADD('2023-01-01', INTERVAL 1 DAY);
        ```
    - `DATEDIFF`: 두 날짜 간의 차이를 반환
        ```sql
        -- '2023-01-10'과 '2023-01-01'의 날짜 차이를 반환
        SELECT DATEDIFF('2023-01-10', '2023-01-01');
        ```

4. 논리 함수(Boolean Functions): 논리 연산을 수행하는 데 사용
    - `IF`: 조건에 따라 다른 값을 반환
        ```sql
        -- 1이 0보다 크면 'true', 그렇지 않으면 'false'를 반환
        SELECT IF(1 > 0, 'true', 'false');
        ```
    - `AND`: 두 조건이 모두 참일 때 참을 반환
        ```sql
        -- 1 AND 1의 결과를 반환
        SELECT 1 AND 1;
        ```
    - `OR`: 두 조건 중 하나가 참일 때 참을 반환
        ```sql
        -- 1 OR 0의 결과를 반환
        SELECT 1 OR 0;
        ```

> ### 왜 사용해야 하는가?
1. **데이터 조작 간편화**: BUILD-IN FUNCTIONS를 사용하면 데이터 조작, 계산, 변환, 조건 처리를 쉽게 수행할 수 있음
2. **코드 재사용성 향상**: 미리 정의된 함수를 사용하여 코드의 재사용성을 높일 수 있음
3. **성능 최적화**: 자주 사용되는 작업을 함수로 정의하여 성능을 최적화할 수 있음

> ### 쉬운 요약
1. BUILD-IN FUNCTIONS는 "데이터베이스에서 자주 사용되는 작업을 쉽게 수행할 수 있도록 미리 정의된 함수들"
    - 주로 문자열 함수, 숫자 함수, 날짜 및 시간 함수, 논리 함수 등이 있음

2. 데이터 조작, 계산, 변환, 조건 처리 등을 쉽게 수행할 수 있음

> ### 비유
1. 주방 도구
    - BUILD-IN FUNCTIONS는 주방에서 "자주 사용되는 도구"와 같음
    - 예: 칼, 도마, 믹서기

2. 소프트웨어 라이브러리
    - BUILD-IN FUNCTIONS는 소프트웨어에서 "자주 사용되는 라이브러리 함수"와 같음
    - 예: 문자열 처리 함수, 수학 함수

[뒤로](mysql.md)
