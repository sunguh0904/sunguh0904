## JavaScript Events
> ### 이벤트 개요 (Event Overview)
브라우저는 클릭, 키보드 입력, 마우스 이동 등이 일어나면 이를 감지하여 특정한 타입의 이벤트를 발생시킴</br>
이벤트가 발생했을 때 호출될 함수를 이벤트 핸들러(Event Handler)라고 하고, 이벤트가 발생했을 때 브라우저에게 이벤트 핸들러의 호출을 위임하는 것을 이벤트 핸들러 등록이라고 함</br>
이벤트와 그에 대응하는 함수(이벤트 핸들러)를 통해 사용자와 애플리케이션은 상호작용할 수 있음

> ### 이벤트 타입 (Event Types)
이벤트 종류를 나타내는 문자열인 이벤트 타입은 약 200여 가지가 있음</br>
이벤트 타입에 대한 상세 목록은 MDN의 [Event reference](https://developer.mozilla.org/ko/docs/Web/Events)에서 확인할 수 있음

> ### 이벤트 핸들러 등록 (Event Handler Registration)
1. HTML 속성으로 등록
    ```html
    <button onclick="alert('Button clicked!')">Click me</button>
    ```

2. DOM 요소의 프로퍼티로 등록
    ```html
    <button id="myButton">Click me</button>
    ```
    ```javascript
    const button = document.getElementById('myButton');
    button.onclick = function() {
        alert('Button clicked!');
    };
    ```

3. addEventListener 메서드로 등록
    ```html
    <button id="myButton">Click me</button>
    ```
    ```javascript
    const button = document.getElementById('myButton');
    button.addEventListener('click', function() {
        alert('Button clicked!');
    });
    ```

> ### 이벤트 핸들러 제거 (Event Handler Removal)
1. DOM 요소의 프로퍼티로 제거
    ```javascript
    button.onclick = null;
    ```

2. removeEventListener 메서드로 제거
    ```javascript
    function handleClick() {
        alert('Button clicked!');
    }
    button.addEventListener('click', handleClick);
    button.removeEventListener('click', handleClick);
    ```

> ### 이벤트 객체 (Event Object)
이벤트가 발생하면 브라우저는 이벤트에 대한 정보를 담고 있는 이벤트 객체를 생성하여 이벤트 핸들러에 전달</br>
이벤트 객체는 이벤트 타입에 따라 다양한 프로퍼티를 가짐

```html
<button id="myButton">Click me</button>
```
```javascript
const button = document.getElementById('myButton');
button.addEventListener('click', function(event) {
    console.log(event.type); // 이벤트 타입 출력
    console.log(event.target); // 이벤트가 발생한 요소 출력
});
```

> ### 이벤트 전파 (Event Propagation)
이벤트가 발생하면 이벤트는 DOM 트리를 통해 전파됨</br>
이벤트 전파는 캡처링 단계, 타깃 단계, 버블링 단계로 나뉨

1. 캡처링 단계: 이벤트가 상위 요소에서 하위 요소로 전파
2. 타깃 단계: 이벤트가 실제 타깃 요소에 도달
3. 버블링 단계: 이벤트가 하위 요소에서 상위 요소로 전파

```html
<div id="parent">
    <button id="child">Click me</button>
</div>
```
```javascript
const parent = document.getElementById('parent');
const child = document.getElementById('child');

parent.addEventListener('click', function() {
    alert('Parent clicked!');
}, true); // 캡처링 단계에서 이벤트 핸들러 실행

child.addEventListener('click', function() {
    alert('Child clicked!');
});
```

> ### 이벤트 위임 (Event Delegation)
이벤트 위임은 상위 요소에 이벤트 핸들러를 등록하여 하위 요소에서 발생한 이벤트를 처리하는 방법</br>
이벤트 위임을 사용하면 많은 하위 요소에 각각 이벤트 핸들러를 등록하지 않아도 됨

```html
<ul id="list">
    <li>Item 1</li>
    <li>Item 2</li>
    <li>Item 3</li>
</ul>
```
```javascript
const list = document.getElementById('list');
list.addEventListener('click', function(event) {
    if (event.target.tagName === 'LI') {
        alert('Item clicked: ' + event.target.textContent);
    }
});
```

[뒤로](javascript.md)
