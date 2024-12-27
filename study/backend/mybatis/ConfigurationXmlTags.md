## MyBatis Configuration XML Tags
> ### MyBatis Configuration XML Tags란?
MyBatis 설정 XML 태그는 MyBatis 프레임워크의 동작을 설정하는 데 사용되는 태그들</br>
주로 데이터베이스 연결 정보, 매퍼 파일 위치, 환경 설정 등을 정의함

> ### 주요 XML 태그
1. `<configuration>`: MyBatis 설정 파일의 루트 요소
    ```xml
    <configuration>
        <!-- 설정 내용 -->
    </configuration>
    ```

2. `<environments>`: 여러 환경 설정을 정의
    ```xml
    <environments default="development">
        <environment id="development">
            <!-- 환경 설정 내용 -->
        </environment>
    </environments>
    ```

3. `<environment>`: 특정 환경 설정을 정의
    ```xml
    <environment id="development">
        <transactionManager type="JDBC"/>
        <dataSource type="POOLED">
            <property name="driver" value="com.mysql.cj.jdbc.Driver"/>
            <property name="url" value="jdbc:mysql://localhost:3306/mydatabase"/>
            <property name="username" value="root"/>
            <property name="password" value="password"/>
        </dataSource>
    </environment>
    ```

4. `<transactionManager>`: 트랜잭션 관리 방식을 설정
    ```xml
    <transactionManager type="JDBC"/>
    ```

5. `<dataSource>`: 데이터베이스 연결 정보를 설정
    ```xml
    <dataSource type="POOLED">
        <property name="driver" value="com.mysql.cj.jdbc.Driver"/>
        <property name="url" value="jdbc:mysql://localhost:3306/mydatabase"/>
        <property name="username" value="root"/>
        <property name="password" value="password"/>
    </dataSource>
    ```

6. `<mappers>`: 매퍼 파일이나 클래스의 위치를 설정
    ```xml
    <mappers>
        <mapper resource="mybatis/mapper/EmployeeMapper.xml"/>
        <mapper class="com.example.mybatis.mapper.DepartmentMapper"/>
    </mappers>
    ```

> ### 왜 사용해야 하는가?
1. **중앙 집중식 설정 관리**: MyBatis 설정을 XML 태그로 중앙에서 관리할 수 있음
2. **유연성**: 다양한 설정을 통해 MyBatis의 동작을 커스터마이징할 수 있음
3. **가독성**: 설정 정보를 XML 형식으로 명확하게 정의할 수 있음

> ### 쉬운 요약
1. MyBatis 설정 XML 태그는 MyBatis 프레임워크의 동작을 설정하는 태그들
    - 주로 데이터베이스 연결 정보, 매퍼 파일 위치, 환경 설정 등을 정의함

2. 주요 XML 태그: `<configuration>`, `<environments>`, `<environment>`, `<transactionManager>`, `<dataSource>`, `<mappers>`

> ### 비유
1. 설정 매뉴얼
    - MyBatis 설정 XML 태그는 MyBatis 프레임워크의 동작을 설정하는 매뉴얼과 같음
    - 예: 데이터베이스 연결 정보, 매퍼 파일 위치, 환경 설정 등을 정의

2. 조리법
    - MyBatis 설정 XML 태그는 MyBatis 프레임워크의 동작을 설정하는 조리법과 같음
    - 예: 데이터베이스 연결 정보, 매퍼 파일 위치, 환경 설정 등을 정의

[뒤로](MyBatis.md)
