## JavaScript Get Element Nodes
> ### 노드 취득 (get element node)
1. id 사용 (use id)
    - `Document.prototype.getElementById` 메서드는 인수로 전달한 id 어트리뷰트 값을 갖는 하나의 요소 노드를 탐색하여 반환
    ```html
    <div id="area1" class="area">
        div 영역
        <p id="area2">p 영역</p>
    </div>
    <div id="area1" class="area">
        div 영역
    </div>
    ```
    ```javascript
    // 요소 노드 취득
    const $elem = document.getElementById('area1');
    // 요소의 스타일 속성을 이용하여 배경색 변경
    $elem.style.backgroundColor = 'skyblue';
    ```

2. 태그명 사용 (use tag name)
    - `Document.prototype/Element.prototype.getElementsByTagName` 메서드는 인수로 전달한 태그 이름을 갖는 모든 요소 노드를 탐색하여 반환
    ```html
    <ul id="food">
        <li>김치찌개</li>
        <li>된장찌개</li>
        <li>고등어구이</li>
    </ul>
    <ul id="drink">
        <li>커피</li>
        <li>콜라</li>
        <li>우유</li>
    </ul>
    ```
    ```javascript
    // DOM 전체에서 li 태그를 모두 탐색하여 반환
    const $lists = document.getElementsByTagName("li");
    console.log($lists); // HTMLCollection - 유사 객체 배열, iterable
    console.log($lists.length); // length를 가지고 있음
    ```

3. 클래스명 사용 (use class name)
    - `Document.prototype/Element.prototype.getElementsByClassName` 메서드는 인수로 전달한 class 어트리뷰트 값을 갖는 모든 요소 노드들을 탐색하여 반환
    ```html
    <ul id="available">
        <li class="drink coffee">커피</li>
        <li class="drink coke">콜라</li>
        <li class="drink milk">우유</li>
    </ul>
    <ul id="unavailable">
        <li class="drink soju">소주</li>
        <li class="drink beer">맥주</li>
    </ul>
    ```
    ```javascript
    // DOM 전체에서 class 값이 drink 인 요소 노드를 모두 탐색하여 반환
    const $drinks = document.getElementsByClassName("drink");
    console.log($drinks); // HTMLCollection - 유사 객체 배열, iterable
    console.log($drinks.length); // length를 가지고 있음
    ```

4. 선택자 사용 (use css)
    - `Document.prototype/Element.prototype.querySelector` 메서드는 인수로 전달한 CSS 선택자를 만족시키는 하나의 요소 노드를 탐색하여 반환
    ```html
    <div class="area">
        <p>first</p>
    </div>
    <div class="area">
        <p>second</p>
    </div>
    ```
    ```javascript
    // DOM 전체에서 class 어트리뷰트 값이 area인 첫 번째 요소 노드를 탐색하여 반환
    const $area = document.querySelector(".area");
    console.log($area);
    // 취득한 요소 노드의 backgroundColor 프로퍼티 값 변경
    $area.style.backgroundColor = 'gray';
    ```

5. HTMLCollection과 NodeList
    - HTMLCollection과 NodeList는 DOM API가 여러 개의 결과 값을 반환하기 위한 DOM 컬렉션 객체
    - HTMLCollection은 `getElementsByTagName`, `getElementsByClassName` 메서드가 반환하는 객체
    - NodeList는 `querySelectorAll` 메서드가 반환하는 객체
    ```html
    <ul>
        <li class='white'>첫 번째 글</li>
        <li class='white'>두 번째 글</li>
        <li class='white'>세 번째 글</li>
    </ul>
    ```
    ```javascript
    const $whiteList = document.getElementsByClassName('white');
    console.log($whiteList);
    Array.from($whiteList).forEach(list => list.className = 'black');
    ```

> ### 왜 사용해야 하는가?
1. **효율적인 탐색**: 다양한 방법으로 요소 노드를 효율적으로 탐색할 수 있음
2. **유연성**: id, 태그명, 클래스명, 선택자 등을 사용하여 요소 노드를 탐색할 수 있음
3. **DOM 컬렉션 활용**: HTMLCollection과 NodeList를 사용하여 여러 개의 결과 값을 처리할 수 있음

> ### 쉬운 요약
1. 요소 노드를 탐색하는 다양한 방법 제공
    - id, 태그명, 클래스명, 선택자 사용
    - HTMLCollection과 NodeList 활용

> ### 비유
1. 지도 탐색
    - 요소 노드 탐색은 "지도에서 특정 위치를 찾는 과정"과 같음
    - 예: id, 태그명, 클래스명, 선택자를 사용하여 특정 위치를 찾음

2. 도서관 검색
    - 요소 노드 탐색은 "도서관에서 책을 찾는 과정"과 같음
    - 예: 다양한 방법으로 책을 검색하고, 여러 권의 책을 처리

[뒤로](javascript.md)
