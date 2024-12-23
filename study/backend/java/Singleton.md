## Singleton
> ### 싱글톤이란?
싱글톤(Singleton)은 한 클래스에 하나의 인스턴스만 생성하도록 보장하는 디자인 패턴</br>
즉, 프로그램 전체에서 해당 클래스의 인스턴스를 하나만 유지하며, 그 인스턴스를 어디서든 접근할 수 있도록 만듦

> ### 싱글톤의 예
- 프린터 관리 시스템
    - 여러 사용자가 프린터를 사용해도, 프린터 관리 시스템은 하나만 있어야 효율적

- 운영 체제의 설정 관리
    - 컴퓨터의 운영 체제 설정은 단일 객체로 관리되며, 모든 프로그램이 동일한 설정을 공유

- 로그 시스템
    - 프로그램의 로그 기록을 관리하는 시스템은 하나의 인스턴스로 공유되어야 효율적으로 관리

> ### 코드로 보기
1. 싱글톤 구현 (Lazy Initialization)
- 필요할 때 인스턴스를 생성하는 방식
    ```java
    public class Singleton {
        // 1. 싱글톤 인스턴스를 저장할 정적 변수
        private static Singleton instance;

        // 2. 생성자를 private으로 설정해 외부에서 인스턴스 생성 방지
        private Singleton() {}

        // 3. 인스턴스에 접근하기 위한 정적 메서드
        public static Singleton getInstance() {
            if (instance == null) {
                instance = new Singleton();  // 처음 호출 시 인스턴스 생성
            }
            return instance;
        }

        // 예제 메서드
        public void showMessage() {
            System.out.println("싱글톤 객체입니다!");
        }
    }
    ```

- 사용 예
    ```java
    public class Main {
        public static void main(String[] args) {
            Singleton obj1 = Singleton.getInstance();
            Singleton obj2 = Singleton.getInstance();

            // 같은 객체를 참조
            System.out.println(obj1 == obj2);  // 출력: true

            obj1.showMessage();  // 출력: 싱글톤 객체입니다!
        }
    }
    ```

> ### 쉬운 요약
1. 싱글톤은 프로그램 전체에서 하나의 객체만 유지하는 패턴
    - 여러 곳에서 동일한 객체를 공유해야 하는 상황에서 사용

2. 장점
    - 전역 상태 관리: 한 곳에서 상태를 관리할 수 있음
    - 메모리 절약: 객체를 한 번만 생성하므로 메모리 낭비를 줄임

3. 단점
    - 테스트하기 어려울 수 있음: 전역 상태가 존재하므로 의존성을 분리하기 힘든 경우가 있음
    - 다중 스레드 환경에서 동기화를 고려해야 함

> ### 비유
1. 대통령
    - 한 나라에 대통령은 한 명만 존재하며, 모든 사람들이 동일한 대통령에게 의존

2. 프린터 관리 시스템
    - 회사에서 여러 사람이 프린터를 사용할 때, 하나의 관리 시스템을 통해 작업을 처리해야 혼란이 없음

3. 운영 체제
    - 컴퓨터는 하나의 운영 체제를 기반으로 작동하며, 모든 프로그램이 동일한 운영 체제를 공유

[뒤로](../README.md#java-study-notes)