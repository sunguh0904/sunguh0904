## Dynamic SQL Mapper
> ### Dynamic SQL Mapper란?
Dynamic SQL Mapper는 MyBatis에서 조건에 따라 동적으로 SQL 쿼리를 생성하는 기능</br>
주로 복잡한 조건문을 처리하거나, 다양한 상황에 맞는 SQL 쿼리를 생성할 때 사용됨

> ### Dynamic SQL Mapper의 주요 기능
1. 조건문 처리: 조건에 따라 SQL 쿼리를 동적으로 생성
    ```xml
    <select id="findActiveBlogWithTitleLike" resultType="Blog">
        SELECT * FROM BLOG
        WHERE state = 'ACTIVE'
        <if test="title != null">
            AND title like #{title}
        </if>
    </select>
    ```

2. 반복문 처리: 반복문을 사용하여 SQL 쿼리를 동적으로 생성
    ```xml
    <select id="selectPostIn" resultType="Post">
        SELECT * FROM POST WHERE ID IN
        <foreach item="id" collection="list" open="(" separator="," close=")">
            #{id}
        </foreach>
    </select>
    ```

3. 트리밍: 불필요한 공백이나 구분자를 제거하여 SQL 쿼리를 동적으로 생성
    ```xml
    <trim prefix="WHERE" prefixOverrides="AND |OR ">
        <if test="state != null">
            AND state = #{state}
        </if>
        <if test="title != null">
            AND title like #{title}
        </if>
    </trim>
    ```

> ### 왜 사용해야 하는가?
1. **유연성**: 다양한 조건에 맞는 SQL 쿼리를 동적으로 생성할 수 있음
2. **코드 간결화**: 복잡한 조건문을 간결하게 처리할 수 있음
3. **유지보수 용이**: SQL 쿼리를 동적으로 생성하여 유지보수가 용이함

> ### 쉬운 요약
1. Dynamic SQL Mapper는 "조건에 따라 동적으로 SQL 쿼리를 생성하는 기능"
    - 주로 복잡한 조건문을 처리하거나, 다양한 상황에 맞는 SQL 쿼리를 생성할 때 사용됨

2. 조건문, 반복문, 트리밍 기능을 제공

> ### 비유
1. 요리 레시피
    - Dynamic SQL Mapper는 "상황에 따라 재료를 다르게 사용하는 요리 레시피"와 같음
    - 예: 특정 재료가 있을 때만 사용하는 조건문

2. 맞춤형 주문
    - Dynamic SQL Mapper는 "고객의 요구에 따라 맞춤형으로 주문을 처리하는 시스템"과 같음
    - 예: 고객의 요구에 따라 다른 재료를 사용하는 조건문

[뒤로](MyBatis.md)
