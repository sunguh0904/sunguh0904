## Static
> ### 스태틱이란?
스태틱(Static)은 클래스에 소속된 정적인 멤버를 의미하며, 객체와 상관없이 클래스 자체에 속함</br>
일반적인 멤버(필드, 메소드)는 객체마다 개별적으로 존재하지만, static 멤버는 클래스가 메모리에 로드될 때 한 번만 생성되며 모든 객체가 공유

> ### 스태틱의 예
- 학교 공통 규칙
    - 학생마다 이름과 학번(인스턴스 멤버)은 다르지만, "학교 규칙"(스태틱 멤버)은 모든 학생이 공유

- 은행 금리
    - 각 계좌의 잔액(인스턴스 멤법)은 다르지만, 은행의 금리(스태틱 멤버)는 모든 계좌가 공유

- 프로그램 설정값
    - 프로그램의 전체 언어 설정은 모든 사용자가 공유하는 공통적인 값

> ### 코드로 보기
1. Static 변수
- 모든 객체가 공유하는 클래스 멤버
    ```java
    public class School {
        public static String schoolName = "Greenwood High";  // Static 변수
        public String studentName;                          // 인스턴스 변수

        public School(String studentName) {
            this.studentName = studentName;
        }

        public void printInfo() {
            System.out.println("학교: " + schoolName + ", 학생: " + studentName);
        }
    }

    public class Main {
        public static void main(String[] args) {
            School.schoolName = "Bluewood High";  // Static 멤버는 클래스 이름으로 접근 가능

            School student1 = new School("Alice");
            School student2 = new School("Bob");

            student1.printInfo();  // 출력: 학교: Bluewood High, 학생: Alice
            student2.printInfo();  // 출력: 학교: Bluewood High, 학생: Bob
        }
    }
    ```

1. Static 메소드
- 객체 없이 호출 가능한 메소드
    ```java
    public class MathUtils {
        public static int add(int a, int b) {
            return a + b;
        }
    }

    public class Main {
        public static void main(String[] args) {
            int sum = MathUtils.add(5, 3);  // 클래스 이름으로 바로 호출
            System.out.println("합계: " + sum);  // 출력: 합계: 8
        }
    }
    ```

> ### 쉬운 요약
1. Static은 클래스에 소속된 멤버
    - 클래스가 로드될 때 메모리에 생성되고, 모든 객체가 공유

2. 주요 특징
    - Static 변수: 모든 객체가 같은 값을 공유
    - Static 메소드: 객체 생성 없이 클래스 이름으로 호출 가능

3. 장점
    - 공통된 데이터를 효율적으로 관리
    - 객체 없이 바로 접근 가능

> ### 비유
1. 학교 규칙
    - 학교의 공통 규칙은 모든 학생이 공유하며, 누구나 동일하게 적용

2. 은행 금리
    - 은행 금리는 모든 계좌에 동일하게 적용되며, 계좌별로 다르지 않음

3. TV 채널 설정
    - TV의 기본 채널 설정은 모든 사용자에게 동일하며, 공유되는 값

[뒤로](java)