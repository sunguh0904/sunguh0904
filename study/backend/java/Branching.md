## Branching
> ### 분기문 이란?
분기문(Branching)은 프로그램이 특정 조건에 따라 다른 경로로 실행되는 것을 의미</br>
"조건에 따라 어느 길로 갈지 결정"하는 것이 바로 분기

비유하자면, 분기문은 "갈림길에서 표지판을 보고 방향을 선택하는 과정"
- 예: 길이 두 갈래로 나뉘어 있고, "비가 오면 오른쪽 길, 안 오면 왼쪽 길로 간다"는 규칙이 있을 때, 그 선택을 분기라고 함

> ### 분기문의 예
- 날씨에 따른 외출 준비
    - "비가 오면 우산을 챙기고, 안 오면 그냥 나간다"

- 식당 메뉴 선택
    - "오늘의 메뉴가 치킨이면 치킨을 먹고, 아니면 피자를 먹는다"

- 교통 상황에 따른 경로 변경
    - "도로가 막히면 지하철로 가고, 막히지 않으면 차를 탄다"

> ### 코드로 보기
1. if-else 분기
- 조건에 따라 다른 동작을 수행
    ```java
    boolean isRaining = true;
    if (isRaining) {
        System.out.println("우산을 챙긴다.");
    } else {
        System.out.println("그냥 나간다.");
    }
    ```

2. switch 분기
- 특정 값에 따라 여러 가지 경로 중 하나를 선택
    ```java
    int menu = 2;
    switch (menu) {
        case 1:
            System.out.println("치킨을 먹는다.");
            break;
        case 2:
            System.out.println("피자를 먹는다.");
            break;
        default:
            System.out.println("메뉴를 고르지 않는다.");
    }
    ```

3. 삼항 연산자로 분기
- 간단한 조건을 짧게 표현
    ```java
    boolean isHungry = true;
    String action = isHungry ? "밥을 먹는다" : "물을 마신다";
    System.out.println(action);  // 출력: 밥을 먹는다
    ```

> ### 쉬운 요약
1.	분기문은 조건에 따라 프로그램의 실행 흐름을 나누는 것
	- 조건을 평가하고, 참이면 한 방향으로, 거짓이면 다른 방향으로 실행

2.	분기문의 종류
	- if-else: 조건에 따라 둘 중 하나를 선택
	- switch: 여러 값 중 하나를 선택
	- 삼항 연산자: 간단한 조건을 짧게 표현

3.	일상적인 판단과 유사
	- 조건을 확인한 후 “어떻게 할지”를 결정하는 행동을 자동화한 것

> ### 비유
1.	갈림길에서 표지판 보기
	- “비가 오면 우산을 챙기고, 안 오면 그냥 나간다”는 갈림길에서 방향을 선택하는 것과 같음

2.	식당 메뉴판
	- “1번을 선택하면 치킨, 2번을 선택하면 피자, 그 외에는 아무것도 먹지 않음”처럼 값을 기준으로 동작이 결정

3.	자동차 내비게이션
	- 교통 상황에 따라 빠른 길을 안내하거나, 막히는 길을 피하는 것처럼 조건에 따라 실행 흐름을 변경

[뒤로](java.md)