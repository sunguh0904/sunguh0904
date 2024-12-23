## DTO
> ### DTO란?
DTO(Data Transfer Object)는 데이터를 전달하기 위한 객체</br>
주로 계층 간(예: 컨트롤러 -> 서비스 -> 데이터베이스) 데이터 교환을 단순화하고 구조화하는 데 사용</br>
DTO는 데이터를 저장하고 전달하느 역할만 하며, 내부에 로직을 포함하지 않음

> ### DTO의 예
- 택배 상자
    - 물건(데이터)을 상자(DTO)에 담아서 보내고, 상자가 아닌 물건만 활용

- 학생 정보 카드
    - 학생의 이름, 나이, 성적 같은 데이터를 적은 카드가 DTO처럼 역할을 수행

- 주문서
    - 주문 정보를 기록한 서류를 전달하는 과정에서 서류는 데이터를 전달에만 사용됨

> ### 코드로 보기
1. DTO 클래스
- 사용자 정보를 담아 전달하는 DTO 예제
    ```java
    public class UserDTO {
        private String name;
        private int age;
        private String email;

        // 생성자
        public UserDTO(String name, int age, String email) {
            this.name = name;
            this.age = age;
            this.email = email;
        }

        // Getter
        public String getName() {
            return name;
        }

        public int getAge() {
            return age;
        }

        public String getEmail() {
            return email;
        }

        // Setter
        public void setName(String name) {
            this.name = name;
        }

        public void setAge(int age) {
            this.age = age;
        }

        public void setEmail(String email) {
            this.email = email;
        }
    }
    ```

2. DTO 사용 예제
- 컨트롤러에서 서비스 계층으로 데이터 전달
    ```java
    public class Main {
        public static void main(String[] args) {
            // 사용자 정보를 담은 DTO 생성
            UserDTO user = new UserDTO("홍길동", 25, "hong@example.com");

            // 서비스 계층에 데이터 전달
            UserService userService = new UserService();
            userService.saveUser(user);
        }
    }

    class UserService {
        public void saveUser(UserDTO user) {
            System.out.println("사용자 저장: " + user.getName() + ", " + user.getAge() + ", " + user.getEmail());
        }
    }
    ```

> ### 쉬운 요약
1. DTO는 데이터를 담아서 전달하는 객체
    - 데이터를 전달할 때 구조를 명확하게 정리하고 관리하기 쉽게 만들어줌

2. 로직 없이 데이터만 포함
    - 데이터를 가공하거나 처리하는 로직은 포함되지 않음

3. 계층 간 데이터 이동에 사용
    - 계층 간 데이터를 주고받을 때 사용되어 코드를 깔끔하게 만듦

> ### 비유
1. 택배 상자
    - 데이터를 담아서 이동만 시키는 상자처럼, DTO는 데이터를 전달만 함

2. 학생 정보 카드
    - 학생의 이름, 나이, 점수 같은 정보를 담아 전달하는 역할

3. 주문서
    - 제품, 수량, 가격 정보를 기록해 전달하지만, 주문서를 읽고 처리하는 일은 다른 시스템에서 수행

[뒤로](java.md)