# MySQL Study Notes
> ### MySQL이란?
MySQL은 오픈 소스 관계형 데이터베이스 관리 시스템(RDBMS)데이터베이스를 관리하고, 데이터를 저장, 수정, 삭제, 검색하는 데 사용됩니다. MySQL은 성능이 뛰어나고 사용이 간편하여 많은 웹 애플리케이션에서 널리 사용됩니다.

> ### MySQL의 주요 기능
1. 데이터 저장 및 관리: 데이터를 테이블 형식으로 저장하고 관리할 수 있습니다.
    ```sql
    CREATE TABLE employees (
        id INT AUTO_INCREMENT PRIMARY KEY,
        name VARCHAR(100),
        position VARCHAR(100),
        salary DECIMAL(10, 2)
    );
    ```

2. 데이터 검색: SQL 쿼리를 사용하여 데이터를 검색할 수 있습니다.
    ```sql
    SELECT * FROM employees WHERE position = 'Manager';
    ```

3. 데이터 삽입, 수정, 삭제: 데이터를 삽입, 수정, 삭제할 수 있습니다.
    ```sql
    INSERT INTO employees (name, position, salary) VALUES ('John Doe', 'Manager', 50000);
    UPDATE employees SET salary = 55000 WHERE id = 1;
    DELETE FROM employees WHERE id = 1;
    ```

4. 트랜잭션 관리: 트랜잭션을 사용하여 데이터의 일관성을 유지할 수 있습니다.
    ```sql
    START TRANSACTION;
    UPDATE employees SET salary = 60000 WHERE id = 2;
    COMMIT;
    ```

> ### 왜 사용해야 하는가?
1. **성능**: MySQL은 빠르고 효율적인 데이터베이스 관리 시스템입니다.
2. **오픈 소스**: MySQL은 오픈 소스 소프트웨어로 무료로 사용할 수 있습니다.
3. **확장성**: MySQL은 대규모 데이터베이스를 처리할 수 있는 확장성을 제공합니다.

> ### 쉬운 요약
1. MySQL은 "오픈 소스 관계형 데이터베이스 관리 시스템"
    - 데이터를 저장, 수정, 삭제, 검색하는 데 사용됨

> ### 비유
1. 도서관
    - MySQL은 "도서관에서 책을 관리하는 시스템"과 같음
    - 예: 책을 추가하고, 수정하고, 삭제하고, 검색하는 과정

2. 파일 캐비닛
    - MySQL은 "파일 캐비닛에서 문서를 관리하는 시스템"과 같음
    - 예: 문서를 저장하고, 수정하고, 삭제하고, 검색하는 과정

## 추가 자료
1. [SELECT: "SELECT로 데이터 꺼내기"](SELECT.md)
2. [ORDER BY: "ORDER BY로 데이터 정렬하기"](ORDER_BY.md)
3. [WHERE: "WHERE로 조건에 맞는 데이터 선택하기"](WHERE.md)
4. [Comparison Operators: "비교 연산자로 데이터 비교하기"](comparison_operators.md)
5. [LIKE: "LIKE로 패턴 매칭 데이터 검색하기"](LIKE.md)
6. [BETWEEN: "BETWEEN으로 범위 내 데이터 선택하기"](BETWEEN.md)
7. [Logical Operators: "논리 연산자로 조건 결합하기"](Logical_Operators.md)
8. [IN: "IN으로 특정 값 목록과 일치하는 데이터 선택하기"](IN.md)
9. [DISTINCT: "DISTINCT로 고유한 값 선택하기"](DISTINCT.md)
10. [LIMIT: "LIMIT로 결과 행 수 제한하기"](LIMIT.md)
11. [JOIN: "JOIN으로 테이블 결합하기"](JOIN.md)
12. [GROUP BY: "GROUP BY로 데이터 그룹화하기"](GROUP_BY.md)
13. [SUBQUERIES: "SUBQUERIES로 서브쿼리 사용하기"](SUBQUERIES.md)
14. [SET OPERATORS: "SET OPERATORS로 쿼리 결과 결합하기"](SET_OPERATORS.md)
15. [DML: "DML로 데이터 조작하기"](DML.md)
16. [TRANSACTION: "TRANSACTION으로 데이터 무결성 유지하기"](TRANSACTION.md)
17. [DDL: "DDL로 데이터베이스 구조 정의하기"](DDL.md)
18. [CONSTRAINTS: "CONSTRAINTS로 데이터 무결성 보장하기"](CONSTRAINTS.md)
19. [DATA TYPES: "DATA TYPES로 데이터 종류 정의하기"](DATA_TYPES.md)
20. [BUILD-IN FUNCTIONS: "BUILD-IN FUNCTIONS로 자주 사용되는 작업 수행하기"](BUILD_IN_FUNCTIONS.md)
21. [VIEW: "VIEW로 가상 테이블 사용하기"](VIEW.md)
22. [INDEX: "INDEX로 데이터 조회 성능 향상하기"](INDEX.md)

[뒤로](/README.md)
