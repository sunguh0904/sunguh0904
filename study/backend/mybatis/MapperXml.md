## MyBatis Mapper XML
> ### Mapper XML이란?
Mapper XML은 MyBatis에서 SQL 쿼리를 정의하고 관리하는 XML 파일</br>
주로 SQL 쿼리와 자바 메서드를 매핑하고, 복잡한 쿼리를 작성하는 데 사용됨

> ### Mapper XML의 주요 요소
1. SELECT 쿼리 매핑: 데이터 조회를 위한 쿼리 정의
    ```xml
    <select id="getEmployee" parameterType="int" resultType="Employee">
        <!-- employees 테이블에서 id가 일치하는 레코드를 조회 -->
        SELECT * FROM employees WHERE id = #{id}
    </select>
    ```

2. INSERT 쿼리 매핑: 데이터 삽입을 위한 쿼리 정의
    ```xml
    <insert id="insertEmployee" parameterType="Employee">
        <!-- employees 테이블에 새로운 레코드를 삽입 -->
        INSERT INTO employees (name, position, salary)
        VALUES (#{name}, #{position}, #{salary})
    </insert>
    ```

3. UPDATE 쿼리 매핑: 데이터 수정을 위한 쿼리 정의
    ```xml
    <update id="updateEmployee" parameterType="Employee">
        <!-- employees 테이블에서 id가 일치하는 레코드를 수정 -->
        UPDATE employees 
        SET name = #{name}, position = #{position}, salary = #{salary}
        WHERE id = #{id}
    </update>
    ```

4. DELETE 쿼리 매핑: 데이터 삭제를 위한 쿼리 정의
    ```xml
    <delete id="deleteEmployee" parameterType="int">
        <!-- employees 테이블에서 id가 일치하는 레코드를 삭제 -->
        DELETE FROM employees WHERE id = #{id}
    </delete>
    ```

5. ResultMap 정의: 복잡한 결과 매핑을 위한 설정
    ```xml
    <resultMap id="employeeMap" type="Employee">
        <!-- employees 테이블의 emp_id 컬럼을 Employee 객체의 id 속성에 매핑 -->
        <id property="id" column="emp_id"/>
        <!-- employees 테이블의 emp_name 컬럼을 Employee 객체의 name 속성에 매핑 -->
        <result property="name" column="emp_name"/>
        <!-- employees 테이블의 emp_position 컬럼을 Employee 객체의 position 속성에 매핑 -->
        <result property="position" column="emp_position"/>
        <!-- employees 테이블의 dept_id 컬럼을 Department 객체의 id 속성에 매핑 -->
        <association property="department" javaType="Department">
            <id property="id" column="dept_id"/>
            <!-- employees 테이블의 dept_name 컬럼을 Department 객체의 name 속성에 매핑 -->
            <result property="name" column="dept_name"/>
        </association>
    </resultMap>
    ```

> ### 왜 사용해야 하는가?
1. **SQL 쿼리 관리**: 복잡한 SQL 쿼리를 XML 파일에서 별도로 관리할 수 있음
2. **유지보수 용이**: SQL 쿼리를 자바 코드와 분리하여 유지보수가 용이함
3. **동적 쿼리 작성**: 조건에 따라 SQL 쿼리를 동적으로 생성할 수 있음

> ### 쉬운 요약
1. Mapper XML은 SQL 쿼리를 정의하고 관리하는 파일
    - SQL 쿼리와 자바 메서드를 매핑하고, 복잡한 쿼리를 작성하는 데 사용됨

2. 주요 기능
    - SELECT, INSERT, UPDATE, DELETE 쿼리 매핑
    - ResultMap을 통한 복잡한 결과 매핑

> ### 비유
1. 요리 레시피북
    - Mapper XML은 데이터베이스 작업을 위한 레시피북과 같음
    - 예: 각각의 SQL 쿼리가 하나의 요리 레시피처럼 정의됨

2. 설계 도면
    - Mapper XML은 데이터베이스 작업의 설계 도면과 같음
    - 예: SQL 쿼리의 구조와 실행 방법을 상세히 정의

[뒤로](MyBatis.md)
