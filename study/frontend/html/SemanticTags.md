## HTML Semantic Tags
> ### 시멘틱 태그란?
시멘틱 태그(Semantic Tags)는 HTML에서 문서의 의미를 명확하게 나타내기 위해 사용되는 태그</br>
주로 문서의 구조를 정의하고, 콘텐츠의 의미를 전달하는 데 사용됨

> ### 주요 시멘틱 태그
1. `<header>`: 문서나 섹션의 헤더를 정의
    ```html
    <!-- 문서의 헤더를 정의 -->
    <header>
        <h1>My Website</h1>
        <nav>
            <ul>
                <li><a href="#home">Home</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </nav>
    </header>
    ```

2. `<nav>`: 내비게이션 링크를 정의
    ```html
    <!-- 내비게이션 링크를 정의 -->
    <nav>
        <ul>
            <li><a href="#home">Home</a></li>
            <li><a href="#about">About</a></li>
            <li><a href="#contact">Contact</a></li>
        </ul>
    </nav>
    ```

3. `<section>`: 문서의 섹션을 정의
    ```html
    <!-- 문서의 섹션을 정의 -->
    <section>
        <h2>About Us</h2>
        <p>This is the about section.</p>
    </section>
    ```

4. `<article>`: 독립적인 콘텐츠를 정의
    ```html
    <!-- 독립적인 콘텐츠를 정의 -->
    <article>
        <h2>Article Title</h2>
        <p>This is an article.</p>
    </article>
    ```

5. `<aside>`: 문서의 주요 콘텐츠와는 별개의 콘텐츠를 정의
    ```html
    <!-- 문서의 주요 콘텐츠와는 별개의 콘텐츠를 정의 -->
    <aside>
        <h2>Related Links</h2>
        <ul>
            <li><a href="#link1">Link 1</a></li>
            <li><a href="#link2">Link 2</a></li>
        </ul>
    </aside>
    ```

6. `<footer>`: 문서나 섹션의 푸터를 정의
    ```html
    <!-- 문서의 푸터를 정의 -->
    <footer>
        <p>&copy; 2023 My Website</p>
    </footer>
    ```

> ### 왜 사용해야 하는가?
1. **문서 구조 정의**: 시멘틱 태그를 사용하면 문서의 구조를 논리적으로 정의할 수 있음
2. **가독성 향상**: 문서를 섹션으로 나누어 가독성을 향상시킬 수 있음
3. **SEO 최적화**: 검색 엔진이 문서의 구조와 의미를 더 잘 이해할 수 있음

> ### 쉬운 요약
1. 시멘틱 태그는 "HTML에서 문서의 의미를 명확하게 나타내기 위해 사용되는 태그"
    - 주로 문서의 구조를 정의하고, 콘텐츠의 의미를 전달하는 데 사용됨

2. 주요 태그: `<header>`, `<nav>`, `<section>`, `<article>`, `<aside>`, `<footer>`

> ### 비유
1. 책의 장과 절
    - 시멘틱 태그는 "책의 장과 절"과 같음
    - 예: 문서를 논리적인 섹션으로 나누어 구조화

2. 건물의 층과 방
    - 시멘틱 태그는 "건물의 층과 방"과 같음
    - 예: 건물을 층과 방으로 나누어 구조화

[뒤로](html.md)
