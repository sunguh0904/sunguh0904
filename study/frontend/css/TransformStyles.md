## CSS Transform Styles
> ### 변형이란?
변형(Transform)은 CSS에서 HTML 요소를 회전, 크기 조정, 기울이기, 이동 등의 변형을 적용하는 데 사용되는 속성</br>
주로 요소의 시각적 효과를 추가하고, 애니메이션을 적용하는 데 사용됨

> ### 주요 변형 스타일 속성
1. `transform`: 요소에 변형을 적용
    ```css
    /* 요소를 45도 회전 */
    div {
        transform: rotate(45deg);
    }
    /* 요소를 1.5배 확대 */
    div {
        transform: scale(1.5);
    }
    /* 요소를 100px 오른쪽으로 이동 */
    div {
        transform: translateX(100px);
    }
    /* 요소를 30도 기울이기 */
    div {
        transform: skew(30deg);
    }
    ```

2. `transform-origin`: 변형의 기준점을 설정
    ```css
    /* 변형의 기준점을 요소의 중앙으로 설정 */
    div {
        transform-origin: center;
    }
    /* 변형의 기준점을 요소의 왼쪽 상단으로 설정 */
    div {
        transform-origin: top left;
    }
    ```

3. `perspective`: 3D 변형의 원근감을 설정
    ```css
    /* 3D 변형의 원근감을 설정 */
    div {
        perspective: 500px;
    }
    ```

4. `transform-style`: 자식 요소의 3D 변형을 유지할지 여부를 설정
    ```css
    /* 자식 요소의 3D 변형을 유지 */
    div {
        transform-style: preserve-3d;
    }
    ```

> ### 왜 사용해야 하는가?
1. **시각적 효과**: 변형 스타일을 사용하면 요소에 다양한 시각적 효과를 추가할 수 있음
2. **애니메이션**: 변형 스타일을 사용하여 요소에 애니메이션 효과를 적용할 수 있음
3. **디자인 개선**: 요소의 회전, 크기 조정, 기울이기, 이동 등을 통해 디자인을 개선할 수 있음

> ### 쉬운 요약
1. 변형은 "CSS에서 HTML 요소를 회전, 크기 조정, 기울이기, 이동 등의 변형을 적용하는 데 사용되는 속성"
    - 주로 요소의 시각적 효과를 추가하고, 애니메이션을 적용하는 데 사용됨

2. 주요 속성: `transform`, `transform-origin`, `perspective`, `transform-style`

> ### 비유
1. 종이 접기
    - 변형 스타일은 "종이 접기"와 같음
    - 예: 종이를 접고, 회전시키고, 기울여서 다양한 모양을 만드는 것처럼, 요소를 변형하여 시각적 효과를 추가

2. 무대 연출
    - 변형 스타일은 "무대 연출"과 같음
    - 예: 무대 소품을 회전시키고, 이동시키고, 크기를 조정하여 공연의 시각적 효과를 개선

[뒤로](css.md)
