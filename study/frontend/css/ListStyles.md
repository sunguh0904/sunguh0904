## CSS List Styles
> ### 목록 스타일이란?
목록 스타일은 CSS에서 HTML 목록의 외관을 꾸미고, 가독성을 향상시키기 위해 사용되는 속성</br>
주로 순서가 있는 목록(ol)과 순서가 없는 목록(ul)의 스타일을 정의하는 데 사용됨

> ### 주요 목록 스타일 속성
1. `list-style-type`: 목록 항목의 마커 유형을 설정
    ```css
    /* 순서가 없는 목록의 마커를 원형으로 설정 */
    ul {
        list-style-type: disc;
    }
    /* 순서가 있는 목록의 마커를 숫자로 설정 */
    ol {
        list-style-type: decimal;
    }
    ```

2. `list-style-position`: 목록 항목의 마커 위치를 설정
    ```css
    /* 목록 항목의 마커를 텍스트 내부에 배치 */
    ul {
        list-style-position: inside;
    }
    /* 목록 항목의 마커를 텍스트 외부에 배치 */
    ol {
        list-style-position: outside;
    }
    ```

3. `list-style-image`: 목록 항목의 마커로 이미지를 사용
    ```css
    /* 목록 항목의 마커로 이미지를 사용 */
    ul {
        list-style-image: url('marker.png');
    }
    ```

4. `list-style`: 목록 스타일의 단축 속성
    ```css
    /* 목록 스타일의 단축 속성을 사용하여 마커 유형과 위치를 설정 */
    ul {
        list-style: square inside;
    }
    ```

> ### 왜 사용해야 하는가?
1. **디자인**: 목록 스타일을 사용하면 목록의 외관을 꾸밀 수 있음
2. **가독성 향상**: 목록의 마커 유형과 위치를 조정하여 가독성을 향상시킬 수 있음
3. **일관성 유지**: 웹 페이지 전체에서 일관된 목록 스타일을 유지할 수 있음

> ### 쉬운 요약
1. 목록 스타일은 "CSS에서 HTML 목록의 외관을 꾸미고, 가독성을 향상시키기 위해 사용되는 속성"
    - 주로 순서가 있는 목록(ol)과 순서가 없는 목록(ul)의 스타일을 정의하는 데 사용됨

2. 주요 속성: `list-style-type`, `list-style-position`, `list-style-image`, `list-style`

> ### 비유
1. 목록 서식
    - 목록 스타일은 "목록 서식"과 같음
    - 예: 목록의 마커 유형과 위치를 조정하여 외관을 꾸밈

2. 책의 목차
    - 목록 스타일은 "책의 목차"와 같음
    - 예: 책의 각 장의 번호와 위치를 조정하여 가독성을 향상

[뒤로](css.md)
