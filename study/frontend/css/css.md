# CSS Study Notes
> ### CSS란?
CSS(Cascading Style Sheets)는 웹 페이지의 스타일을 정의하고, HTML 요소의 레이아웃을 제어하는 데 사용되는 스타일 시트 언어</br>
주로 웹 페이지의 디자인과 레이아웃을 설정하는 데 사용됨

> ### CSS의 주요 기능
1. 스타일 정의: HTML 요소의 스타일을 정의
    ```css
    /* 텍스트 색상과 폰트 크기를 설정 */
    h1 {
        color: blue;
        font-size: 24px;
    }
    ```

2. 레이아웃 제어: HTML 요소의 레이아웃을 제어
    ```css
    /* 요소를 중앙에 배치 */
    .container {
        display: flex;
        justify-content: center;
        align-items: center;
    }
    ```

3. 반응형 디자인: 다양한 화면 크기에 맞게 디자인을 조정
    ```css
    /* 화면 크기에 따라 스타일을 변경 */
    @media (max-width: 600px) {
        body {
            background-color: lightblue;
        }
    }
    ```

4. 애니메이션: HTML 요소에 애니메이션 효과를 추가
    ```css
    /* 요소에 애니메이션 효과를 추가 */
    .box {
        width: 100px;
        height: 100px;
        background-color: red;
        animation: move 2s infinite;
    }

    @keyframes move {
        0% { transform: translateX(0); }
        50% { transform: translateX(100px); }
        100% { transform: translateX(0); }
    }
    ```

> ### 왜 사용해야 하는가?
1. **디자인**: CSS를 사용하면 웹 페이지의 디자인을 쉽게 설정할 수 있음
2. **레이아웃**: CSS를 사용하여 HTML 요소의 레이아웃을 제어할 수 있음
3. **반응형 디자인**: CSS를 사용하여 다양한 화면 크기에 맞게 디자인을 조정할 수 있음

> ### 쉬운 요약
1. CSS는 "웹 페이지의 스타일을 정의하고, HTML 요소의 레이아웃을 제어하는 데 사용되는 스타일 시트 언어"
    - 주로 웹 페이지의 디자인과 레이아웃을 설정하는 데 사용됨

2. 스타일 정의, 레이아웃 제어, 반응형 디자인, 애니메이션 기능을 제공

> ### 비유
1. 옷
    - CSS는 "사람이 입는 옷"과 같음
    - 예: 옷을 입혀서 사람의 외모를 꾸미는 것처럼, CSS로 웹 페이지의 스타일을 꾸밈

2. 건물의 외관
    - CSS는 "건물의 외관"과 같음
    - 예: 건물의 외관을 꾸미고, 레이아웃을 설정하는 것처럼, CSS로 웹 페이지의 디자인과 레이아웃을 설정

## 추가 자료
1. [CSS Selectors: 선택자](Selectors.md)
2. [CSS Font Styles: 글꼴 스타일](FontStyles.md)
3. [CSS Text Styles: 텍스트 스타일](TextStyles.md)
4. [CSS Paragraph Styles: 문단 스타일](ParagraphStyles.md)
5. [CSS List Styles: 목록 스타일](ListStyles.md)
6. [CSS Background Styles: 배경 스타일](BackgroundStyles.md)

[뒤로](/README.md)
