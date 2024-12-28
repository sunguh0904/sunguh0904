## JavaScript Event Propagation
> ### 이벤트 전파 (event propagation)
생성된 이벤트 객체는 이벤트를 발생시킨 DOM 요소인 이벤트 타깃(event target)을 중심으로 DOM 트리를 통해 전파됨

1. 캡처링 단계(capturing phase): 이벤트가 상위 요소에서 하위 요소 방향으로 전파
2. 타깃 단계(target phase): 이벤트가 이벤트 타깃에 도달
3. 버블링 단계(bubbling phase): 이벤트가 하위 요소에서 상위 요소 방향으로 전파

```html
<ul id="drink">
    <li>커피</li>
    <li>콜라</li>
    <li>우유</li>
</ul>
```
```javascript
const $drink = document.getElementById('drink');
$drink.addEventListener('click', e => {
    // ul 영역 클릭 시
    // 2 : 타깃 단계, 타깃도 현재 타깃도 ul로 출력
    // li 영역 클릭 시
    // 3 : 버블링 단계(li->ul), 타깃은 li, 현재 타깃은 ul로 출력
    console.log(e.eventPhase);
    console.log(e.target);
    console.log(e.currentTarget);
});
```

이벤트 핸들러 어트리뷰트/프로퍼티 방식으로 등록한 이벤트 핸들러는 타깃 단계와 버블링 단계의 이벤트만 캐치할 수 있지만, addEventListener 메서드 방식으로 등록한 이벤트 핸들러는 세 번째 인수로 true를 전달하면 캡처링 단계의 이벤트도 캐치할 수 있음

```html
<ul id="food">
    <li>김치찌개</li>
    <li>된장찌개</li>
    <li>고등어구이</li>
</ul>
```
```javascript
const $food = document.getElementById('food');
// 캡쳐링 단계 캐치
$food.addEventListener('click', e => {
    console.log(e.eventPhase);
    console.log(e.target);
    console.log(e.currentTarget);
}, true);
// 버블링 단계 캐치
$food.addEventListener('click', e => {
    console.log(e.eventPhase);
    console.log(e.target);
    console.log(e.currentTarget);
});
// ul 영역 클릭 시 타깃 단계 둘 다 캐치
// li 영역 클릭 시 1 캡처링 단계 -> 3 버블링 단계 캐치
```

> ### 이벤트 위임 (event delegation)
비슷한 방식으로 여러 요소를 다뤄야 할 때 각 요소마다 핸들러를 할당하지 않고, 공통의 조상에 이벤트 핸들러를 단 하나만 할당해 여러 요소를 한 번에 다루는 이벤트 위임을 구현할 수 있음</br>
공통 조상에 할당한 핸들러에서 event.target을 이용하면 실제 어디서 이벤트가 발생했는지 알 수 있으며 이를 이용해 이벤트를 핸들링할 수 있음

```html
<ul id="drink">
    <li>커피</li>
    <li>콜라</li>
    <li>우유</li>
</ul>
```
```javascript
const $drink = document.getElementById('drink');
// 각 li가 클릭 되었을 때 highlight라는 클래스가 없을 경우 부여하고 있을 경우 제거
// li마다 이벤트 핸들러를 등록할수도 있지만 상위 요소인 ul에 한 번만 이벤트 핸들러를 등록
$drink.addEventListener('click', e => {
    // ul 영역 클릭 시에는 동작시키고 싶지 않으므로 li 인지 확인
    if (e.target.matches('li'))
        highlight(e.target); // li가 클릭 되었을 경우 해당 li를 인자로 전달
});
function highlight(li) {
    // 클릭 된 li의 class에 highlight를 부여하거나 제거
    li.classList.toggle('highlight');
}
```

> ### 왜 사용해야 하는가?
1. **유연성**: 이벤트 전파를 통해 다양한 이벤트를 처리할 수 있음
2. **효율성**: 이벤트 위임을 통해 많은 요소에 이벤트 핸들러를 등록하지 않아도 됨
3. **유지보수 용이**: 이벤트 핸들러를 코드에서 쉽게 관리하고 유지보수할 수 있음

> ### 쉬운 요약
1. 이벤트 전파는 "이벤트가 발생한 요소에서 상위 요소로 전파되는 과정"
    - 캡처링 단계, 타깃 단계, 버블링 단계로 나뉨
    - 이벤트 위임을 통해 효율적으로 이벤트를 처리

> ### 비유
1. 물결
    - 이벤트 전파는 "물에 돌을 던졌을 때 생기는 물결"과 같음
    - 예: 물결이 퍼져나가면서 상위 요소로 전파

2. 전염
    - 이벤트 전파는 "전염병이 퍼지는 과정"과 같음
    - 예: 한 사람에게서 시작된 전염병이 주변 사람들에게 퍼짐

[뒤로](javascript.md)
