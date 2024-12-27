## MyBatis Dynamic Query (JAVA Provider)
> ### JAVA Provider란?
JAVA Provider는 MyBatis에서 동적 SQL 쿼리를 자바 코드로 작성할 수 있게 해주는 기능입니다. 주로 복잡한 조건문이나 동적 쿼리를 자바 메서드로 작성하여 관리할 때 사용됩니다.

> ### JAVA Provider의 주요 기능
1. 자바 메서드로 동적 쿼리 작성: 자바 메서드를 사용하여 동적 SQL 쿼리를 생성할 수 있습니다.
    ```java
    public class SqlProvider {
        // 동적 SQL 쿼리를 생성하는 메서드
        public String selectEmployee(Map<String, Object> params) {
            StringBuilder sql = new StringBuilder();
            sql.append("SELECT * FROM employees WHERE 1=1"); // 기본 쿼리
            if (params.get("id") != null) {
                sql.append(" AND id = #{id}"); // id 조건 추가
            }
            if (params.get("name") != null) {
                sql.append(" AND name = #{name}"); // name 조건 추가
            }
            return sql.toString(); // 최종 쿼리 반환
        }
    }
    ```

2. 어노테이션을 사용한 매핑: 자바 메서드를 MyBatis 매퍼 인터페이스에 매핑할 수 있습니다.
    ```java
    // SqlProvider 클래스의 selectEmployee 메서드를 사용하여 쿼리를 실행
    @SelectProvider(type = SqlProvider.class, method = "selectEmployee")
    List<Employee> selectEmployee(Map<String, Object> params);
    ```

> ### 왜 사용해야 하는가?
1. **유연성**: 자바 코드로 동적 쿼리를 작성하여 복잡한 조건문을 유연하게 처리할 수 있음
2. **재사용성**: 자바 메서드를 재사용하여 코드 중복을 줄일 수 있음
3. **유지보수 용이**: 자바 코드로 작성된 동적 쿼리는 유지보수가 용이함

> ### 쉬운 요약
1. JAVA Provider는 "자바 코드로 동적 SQL 쿼리를 작성하는 기능"
    - 주로 복잡한 조건문이나 동적 쿼리를 자바 메서드로 작성하여 관리할 때 사용됨

2. 자바 메서드로 동적 쿼리를 작성하고, 어노테이션을 사용하여 매핑할 수 있음

> ### 비유
1. 요리사
    - JAVA Provider는 "상황에 따라 재료를 다르게 사용하는 요리사"와 같음
    - 예: 특정 재료가 있을 때만 사용하는 조건문

2. 맞춤형 주문
    - JAVA Provider는 "고객의 요구에 따라 맞춤형으로 주문을 처리하는 시스템"과 같음
    - 예: 고객의 요구에 따라 다른 재료를 사용하는 조건문

[뒤로](MyBatis.md)
