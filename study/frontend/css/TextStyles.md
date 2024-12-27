## CSS Text Styles
> ### 텍스트 스타일이란?
텍스트 스타일은 CSS에서 텍스트의 외관을 꾸미고, 가독성을 향상시키기 위해 사용되는 속성</br>
주로 텍스트의 정렬, 장식, 변환 등을 정의하는 데 사용됨

> ### 주요 텍스트 스타일 속성
1. `text-align`: 텍스트의 정렬을 설정
    ```css
    /* 텍스트를 가운데 정렬 */
    p {
        text-align: center;
    }
    ```

2. `text-decoration`: 텍스트의 장식을 설정 (밑줄, 취소선 등)
    ```css
    /* 텍스트에 밑줄을 추가 */
    a {
        text-decoration: underline;
    }
    /* 텍스트의 밑줄을 제거 */
    a {
        text-decoration: none;
    }
    ```

3. `text-transform`: 텍스트의 변환을 설정 (대문자, 소문자 등)
    ```css
    /* 텍스트를 모두 대문자로 변환 */
    h1 {
        text-transform: uppercase;
    }
    /* 텍스트를 모두 소문자로 변환 */
    h1 {
        text-transform: lowercase;
    }
    ```

4. `letter-spacing`: 텍스트의 글자 간격을 설정
    ```css
    /* 텍스트의 글자 간격을 2px로 설정 */
    p {
        letter-spacing: 2px;
    }
    ```

5. `line-height`: 텍스트의 줄 간격을 설정
    ```css
    /* 텍스트의 줄 간격을 1.5로 설정 */
    p {
        line-height: 1.5;
    }
    ```

6. `text-shadow`: 텍스트에 그림자를 추가
    ```css
    /* 텍스트에 그림자를 추가 */
    h1 {
        text-shadow: 2px 2px 5px gray;
    }
    ```

> ### 왜 사용해야 하는가?
1. **디자인**: 텍스트 스타일을 사용하면 텍스트의 외관을 꾸밀 수 있음
2. **가독성 향상**: 텍스트의 정렬, 장식, 변환 등을 조정하여 가독성을 향상시킬 수 있음
3. **일관성 유지**: 웹 페이지 전체에서 일관된 텍스트 스타일을 유지할 수 있음

> ### 쉬운 요약
1. 텍스트 스타일은 "CSS에서 텍스트의 외관을 꾸미고, 가독성을 향상시키기 위해 사용되는 속성"
    - 주로 텍스트의 정렬, 장식, 변환 등을 정의하는 데 사용됨

2. 주요 속성: `text-align`, `text-decoration`, `text-transform`, `letter-spacing`, `line-height`, `text-shadow`

> ### 비유
1. 글씨체
    - 텍스트 스타일은 "글씨체"와 같음
    - 예: 글씨체를 바꾸고, 크기와 색상을 조정하여 텍스트를 꾸밈

2. 옷 스타일
    - 텍스트 스타일은 "옷 스타일"과 같음
    - 예: 옷의 디자인과 색상을 바꾸어 외모를 꾸미는 것처럼, 텍스트의 스타일을 바꾸어 외관을 꾸밈

[뒤로](css.md)
