## CSS Background Styles
> ### 배경 스타일이란?
배경 스타일은 CSS에서 HTML 요소의 배경을 꾸미고, 시각적인 효과를 추가하기 위해 사용되는 속성</br>
주로 배경색, 배경 이미지, 배경 반복 등을 정의하는 데 사용됨

> ### 주요 배경 스타일 속성
1. `background-color`: 요소의 배경색을 설정
    ```css
    /* 요소의 배경색을 연한 회색으로 설정 */
    div {
        background-color: #f0f0f0;
    }
    ```

2. `background-image`: 요소의 배경 이미지를 설정
    ```css
    /* 요소의 배경 이미지로 URL을 설정 */
    div {
        background-image: url('background.jpg');
    }
    ```

3. `background-repeat`: 배경 이미지의 반복 여부를 설정
    ```css
    /* 배경 이미지를 반복하지 않음 */
    div {
        background-repeat: no-repeat;
    }
    /* 배경 이미지를 수평으로 반복 */
    div {
        background-repeat: repeat-x;
    }
    ```

4. `background-position`: 배경 이미지의 위치를 설정
    ```css
    /* 배경 이미지를 중앙에 배치 */
    div {
        background-position: center;
    }
    ```

5. `background-size`: 배경 이미지의 크기를 설정
    ```css
    /* 배경 이미지를 요소의 크기에 맞게 조정 */
    div {
        background-size: cover;
    }
    ```

6. `background`: 배경 스타일의 단축 속성
    ```css
    /* 배경 스타일의 단축 속성을 사용하여 여러 속성을 한 번에 설정 */
    div {
        background: url('background.jpg') no-repeat center/cover;
    }
    ```

> ### 왜 사용해야 하는가?
1. **디자인**: 배경 스타일을 사용하면 요소의 배경을 꾸밀 수 있음
2. **시각적 효과**: 배경 이미지와 색상을 사용하여 시각적인 효과를 추가할 수 있음
3. **일관성 유지**: 웹 페이지 전체에서 일관된 배경 스타일을 유지할 수 있음

> ### 쉬운 요약
1. 배경 스타일은 "CSS에서 HTML 요소의 배경을 꾸미고, 시각적인 효과를 추가하기 위해 사용되는 속성"
    - 주로 배경색, 배경 이미지, 배경 반복 등을 정의하는 데 사용됨

2. 주요 속성: `background-color`, `background-image`, `background-repeat`, `background-position`, `background-size`, `background`

> ### 비유
1. 벽지
    - 배경 스타일은 "벽지"와 같음
    - 예: 벽지의 색상과 패턴을 바꾸어 방의 분위기를 꾸밈

2. 무대 배경
    - 배경 스타일은 "무대 배경"과 같음
    - 예: 무대 배경을 바꾸어 공연의 분위기를 조성

[뒤로](css.md)
