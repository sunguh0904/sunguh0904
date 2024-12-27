## Environment 클래스
> ### Environment 클래스란?
Environment 클래스는 MyBatis에서 환경 설정을 관리하는 데 사용되는 클래스</br>
주로 데이터베이스 연결 정보, 매퍼 설정, 트랜잭션 관리 등을 포함한 설정을 관리함

> ### Environment 클래스의 주요 기능
1. 데이터베이스 연결 설정: 데이터베이스 연결 정보를 설정
    ```java
    Environment environment = new Environment("development", transactionFactory, dataSource);
    ```

2. 트랜잭션 관리: 트랜잭션 관리 방식을 설정
    ```java
    TransactionFactory transactionFactory = new JdbcTransactionFactory();
    ```

3. 매퍼 설정: 매퍼 파일이나 클래스의 위치를 설정
    ```java
    Configuration configuration = new Configuration(environment);
    configuration.addMapper(MyMapper.class);
    ```

> ### 왜 사용해야 하는가?
1. **중앙 집중식 설정 관리**: MyBatis 설정을 중앙에서 관리할 수 있음
2. **유연성**: 다양한 환경에 맞게 설정을 변경할 수 있음
3. **트랜잭션 관리**: 트랜잭션 관리 방식을 설정하여 데이터 무결성을 유지할 수 있음

> ### 쉬운 요약
1. Environment 클래스는 "MyBatis 설정을 관리하는 클래스"
    - 주로 데이터베이스 연결 정보, 매퍼 설정, 트랜잭션 관리 등을 포함한 설정을 관리함

2. 데이터베이스 연결 설정, 트랜잭션 관리, 매퍼 설정 기능을 제공

> ### 비유
1. 설정 관리자
    - Environment 클래스는 "MyBatis 설정을 중앙에서 관리하는 관리자"와 같음
    - 예: 데이터베이스 연결 정보, 트랜잭션 관리 방식을 설정

2. 환경 설정 파일
    - Environment 클래스는 "MyBatis의 환경 설정 파일"과 같음
    - 예: 데이터베이스 연결 정보, 매퍼 설정, 트랜잭션 관리 방식을 설정

[뒤로](MyBatis.md)
