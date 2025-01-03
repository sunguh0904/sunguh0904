## Comparsion
> ### 비교 연산자란?
비교 연산자(Comparsion)는 두 개의 값을 서로 비교하여 관계를 확인하는 작업</br>
"이 값이 더 큰가?", "같은가?", "작은가"?와 같은 질문에 답하기 위해 비교 연산자를 사용

비유하자면, 비교는 저울과 같음
- 저울에 두 물건을 올려놓고 어느 쪽이 더 무거운지 확인하는 것처럼, 비교는 두 값의 관계를 판별
- 예를 들어, 5와 3을 비교할 때 "5는 3보다 크다"는 결과를 얻음

> ### 비교 연산자의 예
- 키 비교
    - "내 키는 170cm이고, 친구의 키는 165cm야. 누가 더 크지?" -> 170 > 165

- 시험 점수 비교
    - "내 점수는 90점이고, 친구 점수는 90점이야. 점수가 같은가?" -> 90 == 90

- 나이 비교
    - "내 나이 20살은 동생 나이 19살보다 많다." -> 20 > 19

> ### 코드로 보기
1. 기본 비교 연산자
- `==`: 두 값이 같은지 확인
- `!=`: 두 값이 다른지 확인
- `>`: 왼쪽 값이 오른쪽 값보다 크거나 같은지 확인
- `>=`: 왼쪽 갑이 오른쪽 값보다 크거나 같은지 확인
- `<=`: 왼쪽 값이 오른쪽 값보다 작거나 같은지 확인
    ```java
    public class ComparisonExample {
        public static void main(String[] args) {
            int a = 5;
            int b = 3;

            System.out.println(a > b);  // true (5는 3보다 크다)
            System.out.println(a < b);  // false (5는 3보다 작지 않다)
            System.out.println(a == b); // false (5는 3과 같지 않다)
            System.out.println(a != b); // true (5는 3과 다르다)
        }
    }
    ```

> ### 쉬운 요약
1. 비교는 두 값을 서로 대조하는 작업
    - "크다", "작다", "같다", "다르다"를 판별

2. 비교 연산자의 종류
    - `==`: 같다
    - `!=`: 다르다
    - `>`: 크다
    - `<`: 작다
    - `>=`: 크거나 같다
    - `<=`: 작거나 같다

3. 비교의 결과는 항상 true 또는 false
    - 비교 연산자는 "참"(true) 또는 "거짓"(false) 값을 반환함

> ### 비유
1. 비교는 저울
    - 두 물건을 올려놓고 어느 쪽이 무거운지 확인하는 것과 같음
    - 예: 5 > 3은 "5가 더 크다"고 판별

2. 점수 비교
    - 시험 점수 두 개를 대조해서 누가 더 높은지 확인하는 것과 비슷

3. 키 순서 비교
    - "누가 더 크지?"를 묻고 대답하는 과정을 떠올리면 됨

[뒤로](java.md)