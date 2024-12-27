## CSS Layout Styles
> ### 레이아웃 스타일이란?
레이아웃 스타일은 CSS에서 HTML 요소의 배치와 정렬을 제어하기 위해 사용되는 속성</br>
주로 요소의 위치, 크기, 정렬 등을 정의하는 데 사용됨

> ### 주요 레이아웃 스타일 속성
1. `display`: 요소의 표시 방식을 설정
    ```css
    /* 요소를 블록 요소로 설정 */
    div {
        display: block;
    }
    /* 요소를 인라인 요소로 설정 */
    span {
        display: inline;
    }
    /* 요소를 플렉스 컨테이너로 설정 */
    .container {
        display: flex;
    }
    ```

2. `position`: 요소의 위치를 설정
    ```css
    /* 요소를 절대 위치로 설정 */
    div {
        position: absolute;
        top: 50px;
        left: 100px;
    }
    /* 요소를 고정 위치로 설정 */
    div {
        position: fixed;
        bottom: 0;
        right: 0;
    }
    ```

3. `flex`: 플렉스 컨테이너와 아이템의 배치를 설정
    ```css
    /* 플렉스 컨테이너 설정 */
    .container {
        display: flex;
        justify-content: center;
        align-items: center;
    }
    /* 플렉스 아이템 설정 */
    .item {
        flex: 1;
    }
    ```

4. `grid`: 그리드 컨테이너와 아이템의 배치를 설정
    ```css
    /* 그리드 컨테이너 설정 */
    .container {
        display: grid;
        grid-template-columns: repeat(3, 1fr);
        grid-gap: 10px;
    }
    /* 그리드 아이템 설정 */
    .item {
        grid-column: span 2;
    }
    ```

5. `float`: 요소를 왼쪽 또는 오른쪽으로 떠 있게 설정
    ```css
    /* 요소를 왼쪽으로 떠 있게 설정 */
    .left {
        float: left;
    }
    /* 요소를 오른쪽으로 떠 있게 설정 */
    .right {
        float: right;
    }
    ```

6. `clear`: 떠 있는 요소의 영향을 제거
    ```css
    /* 떠 있는 요소의 영향을 제거 */
    .clear {
        clear: both;
    }
    ```

> ### 왜 사용해야 하는가?
1. **배치 제어**: 레이아웃 스타일을 사용하면 요소의 배치와 정렬을 제어할 수 있음
2. **디자인**: 요소의 위치와 크기를 조정하여 웹 페이지의 디자인을 개선할 수 있음
3. **반응형 레이아웃**: 다양한 화면 크기에 맞게 레이아웃을 조정할 수 있음

> ### 쉬운 요약
1. 레이아웃 스타일은 "CSS에서 HTML 요소의 배치와 정렬을 제어하기 위해 사용되는 속성"
    - 주로 요소의 위치, 크기, 정렬 등을 정의하는 데 사용됨

2. 주요 속성: `display`, `position`, `flex`, `grid`, `float`, `clear`

> ### 비유
1. 방 배치
    - 레이아웃 스타일은 "방의 가구 배치"와 같음
    - 예: 가구의 위치와 크기를 조정하여 방의 레이아웃을 설정

2. 무대 배치
    - 레이아웃 스타일은 "무대 배치"와 같음
    - 예: 무대의 소품과 배우의 위치를 조정하여 공연의 레이아웃을 설정

[뒤로](css.md)
