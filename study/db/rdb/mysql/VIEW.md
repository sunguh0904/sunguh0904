## VIEW
> ### VIEW란?
VIEW는 하나 이상의 테이블에서 데이터를 조회하는 데 사용되는 가상 테이블</br>
실제 데이터를 저장하지 않고, 쿼리의 결과를 저장하는 데 사용됨

> ### VIEW의 특징
1. 데이터 보안: 민감한 데이터를 숨기고 필요한 데이터만 노출
2. 간편한 쿼리: 복잡한 쿼리를 단순화하여 재사용 가능
3. 데이터 일관성: 여러 테이블의 데이터를 일관되게 조회

> ### VIEW의 종류
1. 단순 뷰(Simple View): 하나의 테이블에서 데이터를 조회
    ```sql
    CREATE VIEW simple_view AS
    SELECT name, position FROM employees;
    ```

2. 복합 뷰(Complex View): 여러 테이블에서 데이터를 조회
    ```sql
    CREATE VIEW complex_view AS
    SELECT e.name, e.position, d.name AS department
    FROM employees e
    JOIN departments d ON e.department_id = d.id;
    ```

3. 업데이트 가능한 뷰(Updatable View): 뷰를 통해 데이터 업데이트 가능
    ```sql
    CREATE VIEW updatable_view AS
    SELECT id, name FROM employees
    WHERE position = 'Manager';
    ```

> ### 왜 사용해야 하는가?
1. **데이터 보안**: 민감한 정보를 숨기고 필요한 데이터만 노출하여 보안을 강화할 수 있음
2. **간편한 쿼리**: 복잡한 쿼리를 단순화하여 재사용 가능, 유지보수가 쉬워짐
3. **데이터 일관성**: 여러 테이블의 데이터를 일관되게 조회하여 데이터 무결성을 유지할 수 있음
4. **성능 향상**: 자주 사용되는 쿼리를 뷰로 만들어 성능을 최적화할 수 있음

> ### 쉬운 요약
1. VIEW는 "하나 이상의 테이블에서 데이터를 조회하는 가상 테이블"
    - 실제 데이터를 저장하지 않고, 쿼리의 결과를 저장

2. 데이터 보안, 간편한 쿼리, 데이터 일관성 등을 제공

> ### 비유
1. 창문을 통해 보는 풍경
    - VIEW는 창문을 통해 "특정 각도에서 보는 풍경"과 같음
    - 예: 창문을 통해 보이는 특정 부분만 볼 수 있음

2. 영화의 특정 장면
    - VIEW는 영화에서 "특정 장면을 재생하는 것"과 같음
    - 예: 전체 영화 중 특정 장면만 볼 수 있음

[뒤로](mysql.md)
