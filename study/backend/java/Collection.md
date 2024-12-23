## Collection
> ### Collection이란?
컬렉션(Collection)은 "데이터를 정리해서 담아두는 통 큰 상자"라고 생각하면 됨</br>
상자에는 다양한 방식으로 물건을 정리할 수 있는데, 순서대로 쌓아 두거나(List), 중복 없이 모아 두거나(Set), 이름표를 붙여 관리(Map)할 수 있음

> ### Collection의 예
1. List
- 순서대로 저장하고, 중복을 허용
- 비유: 책장이 번호 순으로 정리된 책
    ```java
    List<String> books = new ArrayList<>();
    books.add("책1");
    books.add("책2");
    books.add("책1"); // 중복 허용
    System.out.println(books); // 출력: [책1, 책2, 책1]
    ```

2. Set
- 중복 없이 저장하며, 순서는 신경 쓰지 않음
- 비유: 회원 명단에 같은 이름을 여러 번 적지 않음
    ```java
    Set<String> members = new HashSet<>();
    members.add("홍길동");
    members.add("이순신");
    members.add("홍길동"); // 중복 불가
    System.out.println(members); // 출력: [홍길동, 이순신]
    ```

3. Map
- 키(Key) : 값(Value) 쌍으로 데이터를 저장
- 비유: 학생 이름과 점수를 짝지어 기록한 노트
    ```java
    Map<String, Integer> scores = new HashMap<>();
    scores.put("홍길동", 95);
    scores.put("이순신", 87);
    System.out.println(scores); // 출력: {홍길동=95, 이순신=87}
    ```

> ### 코드로 보기
1. List 사용
    ```java
    import java.util.ArrayList;
    import java.util.List;

    public class Main {
        public static void main(String[] args) {
            List<String> list = new ArrayList<>();
            list.add("사과");
            list.add("바나나");
            list.add("사과");
            System.out.println(list); // 출력: [사과, 바나나, 사과]
        }
    }
    ```

2. Set 사용
    ```java
    import java.util.HashSet;
    import java.util.Set;

    public class Main {
        public static void main(String[] args) {
            Set<String> set = new HashSet<>();
            set.add("사과");
            set.add("바나나");
            set.add("사과"); // 중복 추가 불가
            System.out.println(set); // 출력: [사과, 바나나]
        }
    }
    ```

3. Map 사용
    ```java
    import java.util.HashMap;
    import java.util.Map;

    public class Main {
        public static void main(String[] args) {
            Map<String, String> map = new HashMap<>();
            map.put("한국", "서울");
            map.put("일본", "도쿄");
            System.out.println(map); // 출력: {한국=서울, 일본=도쿄}
        }
    }
    ```

> ### 쉬운 요약
1. 컬렉션은 "데이터를 정리하고 보관하는 상자"
    - 여러 데이터를 한곳에 모아 정리해서 저장하고 꺼낼 수 있음

2. 컬렉션에는 종류가 여러 가지
    - List: 순서대로 저장하고 중복 허용
    - Set: 중복 없이 저장, 순서는 상관 없음
    - Map: 키와 값을 짝지어 저장

3. 프로그램에서 데이터 관리가 편리해짐
    - 데이터를 효율적으로 저장, 검색, 삭제할 수 있도록 설계

> ### 비유
1. List는 책장
    - 책이 순서대로 정리된 책장처럼 데이터를 저장하며, 같은 책을 여러 번 넣을 수 있음

2. Set은 명단
    - 중복을 허용하지 않는 회원 명단처럼, 같은 데이터를 중복해서 저장하지 않음

3. Map은 전화번호부
    - 이름과 전화번호를 쌍으로 저장하는 전화번호부처럼, 키와 값을 짝지어 데이터를 저장

[뒤로](java)