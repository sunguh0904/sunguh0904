# MyBatis Study Notes

## MyBatis
> ### MyBatis란?
MyBatis는 자바 객체와 SQL 데이터베이스를 연결해주는 퍼시스턴스 프레임워크</br>
주로 SQL 매핑을 통해 데이터베이스와의 상호작용을 단순화함

> ### MyBatis의 주요 기능
1. SQL 매핑: SQL 쿼리를 XML 파일이나 어노테이션으로 매핑
    ```xml
    <select id="selectEmployee" parameterType="int" resultType="Employee">
        SELECT * FROM employees WHERE id = #{id}
    </select>
    ```

2. 동적 SQL: 조건에 따라 SQL 쿼리를 동적으로 생성
    ```xml
    <select id="findActiveBlogWithTitleLike" resultType="Blog">
        SELECT * FROM BLOG
        WHERE state = 'ACTIVE'
        <if test="title != null">
            AND title like #{title}
        </if>
    </select>
    ```

3. 캐싱: 쿼리 결과를 캐싱하여 성능을 향상
    ```xml
    <cache/>
    ```

> ### 왜 사용해야 하는가?
1. **생산성 향상**: SQL 매핑을 통해 데이터베이스와의 상호작용을 단순화하여 개발 생산성을 높일 수 있음
2. **유연성**: XML 파일이나 어노테이션을 사용하여 SQL 쿼리를 유연하게 관리할 수 있음
3. **성능 최적화**: 캐싱 기능을 통해 쿼리 성능을 최적화할 수 있음

> ### 쉬운 요약
1. MyBatis는 "자바 객체와 SQL 데이터베이스를 연결해주는 퍼시스턴스 프레임워크"
    - 주로 SQL 매핑을 통해 데이터베이스와의 상호작용을 단순화함

2. SQL 쿼리의 매핑, 동적 SQL 생성, 캐싱 기능을 제공

> ### 비유
1. 번역기
    - MyBatis는 "자바 객체와 SQL 데이터베이스 간의 번역기"와 같음
    - 예: 자바 객체를 SQL 쿼리로 변환하거나, SQL 쿼리 결과를 자바 객체로 변환

2. 조리법
    - MyBatis는 "데이터베이스와의 상호작용을 위한 조리법"과 같음
    - 예: XML 파일이나 어노테이션을 사용하여 SQL 쿼리를 정의하고 실행

## 추가 자료
1. [Environment 클래스: MyBatis 설정을 관리하는 클래스](Environment.md)
2. [Configuration 클래스: MyBatis 설정 정보를 관리하는 클래스](Configuration.md)
3. [SqlSessionFactory와 SqlSessionFactoryBuilder 클래스: SQL 세션을 생성하고 관리하는 클래스](SqlSessionFactory.md)
4. [SqlSession 클래스: SQL 쿼리를 실행하고 데이터베이스와 상호작용하는 클래스](SqlSession.md)
5. [MyBatis 설정 XML 파일 작성 방법](ConfigXml.md)

[뒤로](/README.md)
