## JavaScript Event Default Actions
> ### 브라우저 기본 동작 중단 (prevent browser action)
이벤트 객체의 preventDefault 메서드는 DOM 요소의 기본 동작을 중단시킴</br>
예를 들어 a 요소를 클릭하면 href 어트리뷰트에 지정된 링크로 이동하고, checkbox 또는 radio 요소를 클릭하면 체크 또는 해제되는 것 등을 기본 동작이라 함

```html
<a href="https://www.google.com">클릭해도 절대 이동할 수 없는 a태그</a>
<input type="checkbox">클릭해도 절대 체크되지 않는 체크박스
```
```javascript
document.querySelector('a').addEventListener('click', e => {
    e.preventDefault();
});
document.querySelector('input[type=checkbox]').addEventListener('click', e => {
    e.preventDefault();
});
```

> ### 이벤트 전파 방지 (stop event propagation)
이벤트 객체의 stopPropagation 메서드는 이벤트 전파를 중지시킴

```html
<ul id="drink">
    <li>커피</li>
    <li>콜라</li>
    <li>우유</li>
</ul>
```
```javascript
const $drink = document.getElementById('drink');
// 이벤트 위임 - 클릭된 하위 li 요소의 color 변경
$drink.addEventListener('click', e => {
    if (e.target.matches('li'))
        e.target.style.color = 'red';
});
// 첫번째 li를 대상으로 color 변경
document.querySelector('li').addEventListener('click', e => {
    e.stopPropagation(); // 이벤트 전파 중단으로 red로 변경되지 않음
    e.target.style.color = 'blue';
});
```

> ### 왜 사용해야 하는가?
1. **기본 동작 제어**: preventDefault 메서드를 사용하여 DOM 요소의 기본 동작을 중단할 수 있음
2. **이벤트 전파 제어**: stopPropagation 메서드를 사용하여 이벤트 전파를 중지할 수 있음
3. **유연성**: 기본 동작과 이벤트 전파를 제어하여 원하는 동작을 구현할 수 있음

> ### 쉬운 요약
1. preventDefault 메서드는 "DOM 요소의 기본 동작을 중단"
2. stopPropagation 메서드는 "이벤트 전파를 중지"

> ### 비유
1. 신호등
    - preventDefault 메서드는 "신호등에서 빨간불을 켜서 차량의 이동을 중단하는 것"과 같음
    - 예: 차량의 이동을 중단하여 사고를 방지

2. 방화벽
    - stopPropagation 메서드는 "방화벽을 설치하여 불이 퍼지는 것을 막는 것"과 같음
    - 예: 불이 퍼지는 것을 막아 피해를 최소화

[뒤로](javascript.md)
