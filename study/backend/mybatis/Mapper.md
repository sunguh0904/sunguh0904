## Mapper 클래스
> ### Mapper 클래스란?
Mapper 클래스는 MyBatis에서 SQL 쿼리를 자바 인터페이스로 매핑하는 데 사용되는 클래스</br>
주로 데이터베이스 작업을 수행하는 메서드를 정의하고, XML 파일이나 어노테이션으로 SQL 쿼리를 매핑함

> ### Mapper 클래스의 주요 기능
1. 인터페이스 정의: SQL 쿼리를 실행할 메서드를 정의
    ```java
    public interface EmployeeMapper {
        // SELECT 쿼리 매핑
        @Select("SELECT * FROM employees WHERE id = #{id}")
        Employee getEmployeeById(int id);

        // INSERT 쿼리 매핑
        @Insert("INSERT INTO employees (name, position) VALUES (#{name}, #{position})")
        void insertEmployee(Employee employee);

        // UPDATE 쿼리 매핑
        @Update("UPDATE employees SET name = #{name}, position = #{position} WHERE id = #{id}")
        void updateEmployee(Employee employee);

        // DELETE 쿼리 매핑
        @Delete("DELETE FROM employees WHERE id = #{id}")
        void deleteEmployee(int id);
    }
    ```

2. XML 매핑: XML 파일에서 SQL 쿼리를 매핑
    ```xml
    <?xml version="1.0" encoding="UTF-8" ?>
    <!DOCTYPE mapper PUBLIC "-//mybatis.org//DTD Mapper 3.0//EN"
        "http://mybatis.org/dtd/mybatis-3-mapper.dtd">
    <mapper namespace="com.example.mapper.EmployeeMapper">
        <!-- SELECT 쿼리 매핑 -->
        <select id="getEmployeeById" resultType="Employee">
            SELECT * FROM employees WHERE id = #{id}
        </select>

        <!-- INSERT 쿼리 매핑 -->
        <insert id="insertEmployee">
            INSERT INTO employees (name, position)
            VALUES (#{name}, #{position})
        </insert>

        <!-- UPDATE 쿼리 매핑 -->
        <update id="updateEmployee">
            UPDATE employees
            SET name = #{name}, position = #{position}
            WHERE id = #{id}
        </update>

        <!-- DELETE 쿼리 매핑 -->
        <delete id="deleteEmployee">
            DELETE FROM employees WHERE id = #{id}
        </delete>
    </mapper>
    ```

> ### 왜 사용해야 하는가?
1. **코드 간결화**: SQL 쿼리를 자바 인터페이스로 매핑하여 코드를 간결하게 작성할 수 있음
2. **유지보수 용이**: SQL 쿼리를 XML 파일이나 어노테이션으로 분리하여 유지보수가 용이함
3. **타입 안전성**: 컴파일 시점에 타입 체크가 가능하여 안전한 코드 작성이 가능함

> ### 쉬운 요약
1. Mapper 클래스는 SQL 쿼리를 자바 인터페이스로 매핑하는 클래스
    - SQL 쿼리를 실행할 메서드를 정의하고, XML 파일이나 어노테이션으로 SQL 쿼리를 매핑함

2. 주요 기능
    - 인터페이스로 메서드 정의: SELECT, INSERT, UPDATE, DELETE 등의 메서드 정의
    - XML 매핑: XML 파일에서 SQL 쿼리를 매핑

> ### 비유
1. 계약서
    - Mapper 클래스는 데이터베이스와의 계약서와 같음
    - 예: 어떤 데이터를 어떻게 조회, 삽입, 수정, 삭제할지 정의

2. 설계도
    - Mapper 클래스는 데이터베이스 작업의 설계도와 같음
    - 예: SQL 쿼리를 실행할 메서드의 구조와 동작을 정의

[뒤로](MyBatis.md)
