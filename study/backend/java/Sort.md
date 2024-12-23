## Sort
> ### 정렬이란?
정렬(Sort)은 데이터를 특정 순서로 정리하는 작업</br>
"크기 순으로 나열하기", "사전순으로 정리하기"처럼 데이터를 보기 쉽고, 찾기 쉽게 만드는 과정

비유하자면, 정렬은 "책을 키 순서대로 정리하는 책장"과 같음
- 작은 책부터 큰 책까지 나열하거나, 제목의 알파벳 순서대로 정리하면 원하는 책을 쉽게 찾을 수 있음

> ### 정렬의 예
- 책 정리
	- “책을 작은 크기부터 큰 크기까지 정렬”하거나, “제목의 가나다 순으로 정리”

- 학생 성적표
	- “학생들의 성적을 높은 점수에서 낮은 점수 순으로 정렬”

- 파일 이름 정리
	- “파일을 날짜 순, 이름 순으로 정렬”

> ### 코드로 보기
1. 숫자를 오름차순 정렬
    ```java
    import java.util.Arrays;

    public class SortExample {
        public static void main(String[] args) {
            int[] numbers = {5, 3, 8, 1, 2};
            Arrays.sort(numbers);  // 정렬 실행
            System.out.println(Arrays.toString(numbers));  // 출력: [1, 2, 3, 5, 8]
        }
    }
    ```

2. 문자열을 알파벳 순으로 정렬
    ```java
    import java.util.Arrays;

    public class SortExample {
        public static void main(String[] args) {
            String[] names = {"Charlie", "Alice", "Bob"};
            Arrays.sort(names);  // 정렬 실행
            System.out.println(Arrays.toString(names));  // 출력: [Alice, Bob, Charlie]
        }
    }
    ```

> ### 쉬운 요약
1.	정렬은 데이터를 보기 쉽게 정리하는 작업
	- 숫자, 문자, 객체 등 다양한 데이터를 정렬할 수 있음

2.	정렬의 두 가지 방향
	- 오름차순(Ascending): 작은 값에서 큰 값으로 정렬
	- 내림차순(Descending): 큰 값에서 작은 값으로 정렬

3.	정렬은 효율적인 데이터 탐색을 위해 중요
	- 데이터가 정렬되어 있으면 검색, 계산 등이 훨씬 빨라짐

> ### 비유
1.	책장 정리
	- “작은 책부터 큰 책까지 정리”하거나, “제목 순으로 나열”

2.	학생 줄 세우기
	- “키 순서대로 줄을 서세요!“라고 하면, 가장 작은 학생부터 큰 학생까지 순서대로 정렬

3.	도서관 카드목록
	- 책 제목을 가나다 순으로 정리하면 원하는 책을 쉽게 찾을 수 있는 원리와 같음

[뒤로](java.md)