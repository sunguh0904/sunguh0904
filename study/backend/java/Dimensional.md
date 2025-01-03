## Dimensional
> ### 다중 배열이란?
다중 배열(Dimensional)은 데이터를 배열로 표현할 때, 배열 안에 배열이 존재하는 구조를 의미</br>
일반 배열은 한 줄(1차원)로 데이터를 나열하는 반면, 다중 배열은 여러 줄과 칸으로 이루어진 표와 같은 구조를 가짐

비유하자면, 다중 배열은 "좌표가 있는 지도"와 같음
- 1차원 배열은 한 줄에만 데이터가 있는 지도처럼 단순
- 다중 배열(2차원)은 행과 열로 나뉜 좌표가 있는 지도와 같아서, 데이터를 더 구조적으로 표현할 수 있음

> ### 다중 배열의 예
- 엑셀 표
    - 엑셀의 행과 열처럼 데이터를 행(row)과 열(column)에 나누어 저장
    - 예: [ [1, 2], [3, 4], [5, 6] ]

- 좌석 배치도
    - "A형 1열"에 앉은 사람, "B행 2열"에 앉은 사람처럼 위치를 기준으로 데이터를 관리

- 게임 지도
    - "x, y 좌표"에 따라 캐릭터가 있는 위치를 표시

> ### 코드로 보기
1. 2차원 배열 선언과 초기화
    ```java
    int[][] matrix = {
        {1, 2, 3},
        {4, 5, 6},
        {7, 8, 9}
    };
    ```

2. 2차원 배열 값에 접근
- 배열의 값은 행(row)과 열(column)의 인덱스를 사용해 접근
    ```java
    System.out.println(matrix[0][0]); // 출력: 1 (첫 번째 행, 첫 번째 열)
    System.out.println(matrix[1][2]); // 출력: 6 (두 번째 행, 세 번째 열)
    ```

3. 중첩 반복문으로 모든 값 출력
    ```java
    for (int i = 0; i < matrix.length; i++) {
        for (int j = 0; j < matrix[i].length; j++) {
            System.out.print(matrix[i][j] + " ");
        }
        System.out.println();
    }
    // 출력:
    // 1 2 3
    // 4 5 6
    // 7 8 9
    ```

> ### 쉬운 요약
1.	다중 배열은 “배열 안에 배열”
	- 데이터가 행(row)과 열(column)로 구성된 구조

2.	인덱스로 데이터에 접근
	- 배열[행][열] 형태로 데이터를 저장하거나 가져옴

3.	반복문을 활용하여 효율적으로 처리 가능
	- 중첩 반복문을 사용해 모든 데이터를 탐색하거나 출력

> ### 비유
1.	엑셀 표
	- “2행 3열에 있는 값은?“처럼 행과 열을 기준으로 데이터를 찾음
	- 예: matrix[1][2]는 2행 3열에 있는 값

2.	영화관 좌석 배치도
	- “B행 4열에 앉아 있는 사람은 누구인가?“와 같은 구조로 데이터를 저장

3.	게임 지도 좌표
	- “x=1, y=2 위치에 뭐가 있지?“처럼 좌표로 데이터를 찾는 방식과 같음

[뒤로](java.md)