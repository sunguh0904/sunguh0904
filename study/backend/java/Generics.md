## Generics
> ### Generics란?
제네릭(Generics)은 "다양한 크기의 물건을 담을 수 있는 상자"</br>
예를 들어, 일반 상자는 무엇을 담아야 하는지 명확하지 않아 사용할 때마다 확인</br>
하지만 제네릭 상자는 "이 상자는 신발 전용", "이 상자는 책 전용" 처럼 담을 물건의 종류를 미리 정할 수 있음</br>
이렇게 하면 상자를 잘못 사용하는 일이 줄어들고, 더 효율적으로 관리할 수 있음

> ### Generics의 예
1. 제네릭을 사용하지 않는 경우
- 아무 상자나 사용해 물건을 담는 것과 같음, 잘못 담아도 알 수 없음
    ```java
    List list = new ArrayList();
    list.add("사과");
    list.add(10); // 문자열과 숫자를 같이 담아도 컴파일 에러 없음
    String fruit = (String) list.get(0); // 직접 캐스팅 필요
    ```

2. 제네릭을 사용하지 않는 경우
- "이 상자는 사과 전용" 처럼, 특정 데이터 타입만 담을 수 있도록 지정
    ```java
    List<String> list = new ArrayList<>();
    list.add("사과");
    // list.add(10); // 컴파일 에러 발생: 정해진 타입 외에는 담을 수 없음
    String fruit = list.get(0); // 캐스팅 없이 안전하게 값을 꺼낼 수 있음
    ```

> ### 코드로 보기
1. 제네릭 클래스
    ```java
    public class Box<T> {
        private T item;

        public void setItem(T item) {
            this.item = item;
        }

        public T getItem() {
            return item;
        }
    }
    ```
    ```java
    Box<String> stringBox = new Box<>();
    stringBox.setItem("Hello");
    System.out.println(stringBox.getItem()); // 출력: Hello
    ```

2. 제네릭 메소드
    ```java
    public static <T> void printItem(T item) {
        System.out.println(item);
    }
    ```
    ```java
    printItem(10);       // 출력: 10
    printItem("Hello");  // 출력: Hello
    ```

3. 와일드카드 사용
    ```java
    public void printList(List<?> list) {
        for (Object item : list) {
            System.out.println(item);
        }
    }
    ```

> ### 쉬운 요약
1. 제네릭은 "특정한 물건만 담을 수 있는 전용 상자"
    - 예를 들어, "사과 전용 상자"에 사과만 담을 수 있고, 다른 물건은 담을 수 없음
    - 이렇게 하면 잘못된 물건을 담는 실수를 줄이고, 더 안전하게 사용할 수 있음

2. 제네릭은 코드를 더 안전하고 유연하게 만듦
    - 잘못된 데이터 타입을 처리하는 오류를 방지
    - 다양한 데이터 타입을 처리하는 코드를 쉽게 재사용할 수 있음

3. 제네릭은 "컴파일 시점에 실수를 잡아주는 도구"
    - 데이터를 잘못 처리할 가능성을 줄이고, 실행 전에 문제가 있는 코드를 미리 확인할 수 있음

> ### 비유
1. 제네릭은 이름표가 붙은 상자
    - "신발 상자"에는 신발만 넣을 수 있고, "책 상자"에는 책만 넣을 수 있음
    - 프로그램에서 제네릭은 이렇게 상자를 사용할 때 담을 물건(데이터 타입)을 정하는 역할

2. 제네릭은 안전한 장바구니
    - 자압구니에 "사과만 담아야 한다"고 정하면, 실수로 오렌지를 담으려고 할 때 바로 오류를 알려줌
    - 프로그램에서도 "이 변수는 숫자만 받아야 한다"고 지정하면 다른 타입은 받을 수 있음

[뒤로](../README.md#java-study-notes)