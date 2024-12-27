## CSS Animation Styles
> ### 애니메이션이란?
애니메이션(Animation)은 CSS에서 HTML 요소에 애니메이션 효과를 추가하여 시각적인 변화를 주는 데 사용되는 속성</br>
주로 요소의 속성 값을 시간에 따라 변화시켜 다양한 애니메이션 효과를 구현하는 데 사용됨

> ### 주요 애니메이션 스타일 속성
1. `@keyframes`: 애니메이션의 단계별 변화를 정의
    ```css
    /* 애니메이션의 단계별 변화를 정의 */
    @keyframes move {
        0% { transform: translateX(0); }
        50% { transform: translateX(100px); }
        100% { transform: translateX(0); }
    }
    ```

2. `animation-name`: 적용할 애니메이션의 이름을 설정
    ```css
    /* 요소에 적용할 애니메이션의 이름을 설정 */
    .box {
        animation-name: move;
    }
    ```

3. `animation-duration`: 애니메이션의 지속 시간을 설정
    ```css
    /* 애니메이션의 지속 시간을 2초로 설정 */
    .box {
        animation-duration: 2s;
    }
    ```

4. `animation-timing-function`: 애니메이션의 속도 곡선을 설정
    ```css
    /* 애니메이션의 속도 곡선을 ease로 설정 */
    .box {
        animation-timing-function: ease;
    }
    ```

5. `animation-delay`: 애니메이션의 시작 시간을 지연
    ```css
    /* 애니메이션의 시작 시간을 1초 지연 */
    .box {
        animation-delay: 1s;
    }
    ```

6. `animation-iteration-count`: 애니메이션의 반복 횟수를 설정
    ```css
    /* 애니메이션을 무한히 반복 */
    .box {
        animation-iteration-count: infinite;
    }
    ```

7. `animation-direction`: 애니메이션의 진행 방향을 설정
    ```css
    /* 애니메이션을 역방향으로 진행 */
    .box {
        animation-direction: reverse;
    }
    ```

8. `animation`: 애니메이션 스타일의 단축 속성
    ```css
    /* 애니메이션 스타일의 단축 속성을 사용하여 여러 속성을 한 번에 설정 */
    .box {
        animation: move 2s ease 1s infinite reverse;
    }
    ```

> ### 왜 사용해야 하는가?
1. **시각적 효과**: 애니메이션 스타일을 사용하면 요소에 다양한 시각적 효과를 추가할 수 있음
2. **사용자 경험 향상**: 애니메이션을 통해 사용자 경험을 향상시킬 수 있음
3. **디자인 개선**: 요소의 속성 값을 시간에 따라 변화시켜 디자인을 개선할 수 있음

> ### 쉬운 요약
1. 애니메이션은 "CSS에서 HTML 요소에 애니메이션 효과를 추가하여 시각적인 변화를 주는 속성"
    - 주로 요소의 속성 값을 시간에 따라 변화시켜 다양한 애니메이션 효과를 구현하는 데 사용됨

2. 주요 속성: `@keyframes`, `animation-name`, `animation-duration`, `animation-timing-function`, `animation-delay`, `animation-iteration-count`, `animation-direction`, `animation`

> ### 비유
1. 만화 영화
    - 애니메이션 스타일은 "만화 영화"와 같음
    - 예: 만화 영화에서 캐릭터가 움직이는 것처럼, 요소에 애니메이션 효과를 추가하여 시각적인 변화를 줌

2. 무대 연출
    - 애니메이션 스타일은 "무대 연출"과 같음
    - 예: 무대에서 배우가 움직이고, 조명이 변화하는 것처럼, 요소에 애니메이션 효과를 추가하여 시각적인 변화를 줌

[뒤로](css.md)
