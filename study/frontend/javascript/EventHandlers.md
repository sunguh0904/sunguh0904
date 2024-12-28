## JavaScript Event Handlers
> ### 이벤트 핸들러 등록 (Event Handler Registration)
이벤트가 발생했을 때 브라우저에게 이벤트 핸들러의 호출을 위임하는 것을 이벤트 핸들러 등록이라고 하며, 이벤트 핸들러를 등록하는 방법은 3가지가 있음

> ### HTML 이벤트 핸들러 어트리뷰트 (event handler attribute)
HTML 이벤트 핸들러 어트리뷰트 (on 접두사 + 이벤트 타입) 값으로 함수 호출문을 할당하여 이벤트 핸들러를 등록하는 방식</br>
주의할 점은 함수 참조가 아닌 함수 호출문을 할당한다는 것

```html
<button onclick="alert('클릭했네?'); console.log('클릭했네?');">클릭해보세요</button>
<button onmouseover="hello('수강생');">마우스를 올려보세요</button>
<script>
function hello(name){
    alert(`${name}씨, 마우스 올리지마세요!`);
}
</script>
```

> ### 이벤트 핸들러 프로퍼티 (event handler property)
window 객체와 Document, HTMLElement 타입의 DOM 노드 객체는 이벤트에 대응하는 이벤트 핸들러 프로퍼티를 가지고 있음</br>
이벤트 핸들러 프로퍼티의 키는 이벤트 핸들러 어트리뷰트와 동일하며 (on 접두사 + 이벤트 타입) 이벤트 핸들러 프로퍼티에 함수를 바인딩하면 이벤트 핸들러가 등록됨</br>
이벤트 핸들러 어트리뷰트 방식과 비교했을 때 HTML과 자바스크립트가 뒤섞이는 문제는 해결할 수 있지만 이벤트 핸들러 프로퍼티에 하나의 이벤트 핸들러만 바인딩 할 수 있다는 단점이 있음

```html
<button id="btn">클릭해보세요</button>
<script>
const $button = document.querySelector('#btn');
$button.onclick = function() {
    alert('DOM 프로퍼티 방식으로 이벤트 핸들러 등록 완료!');
};
// 이전 이벤트 핸들러는 무시되어 하나의 이벤트 밖에 연결 할 수 없음
$button.onclick = () => alert('이벤트 덮어쓰기!');
</script>
```

> ### addEventListener 메서드 (addEventListener method)
EventTarget.prototype.addEventListener 메서드를 사용하여 이벤트를 등록할 수 있음</br>
EventTarget.addEventListener('eventType', functionName [, useCapture])</br>
첫 번째 매개변수에는 이벤트 타입, 두 번째 매개변수에는 이벤트 핸들러를 전달하고 마지막 매개변수에는 이벤트 전파 단계(캡처링 또는 버블링)을 지정</br>
addEventListener 메서드 방식은 이벤트 핸들러 프로퍼티에 바인딩 된 이벤트 핸들러에 아무런 영향을 주지 않음</br>
동일한 HTML 요소에서 발생한 동일한 이벤트에 대해 addEventListener 메서드 방식으로는 하나 이상의 이벤트 핸들러를 등록 할 수 있으며, 이때 이벤트 핸들러는 등록된 순서대로 호출됨

```html
<button id="btn">클릭해보세요</button>
<script>
const $button = document.getElementById('btn');
$button.addEventListener('click', function () {
    alert('클릭했네?');
});
// 이벤트 핸들러 프로퍼티 방식 추가
$button.onclick = function () {
    console.log('이벤트 핸들러 프로퍼티 방식으로 이벤트 핸들러 등록!');
}
// addEventListener 메소드 방식 하나 더 추가
$button.addEventListener('click', function () {
    console.log('addEventListener 메소드 방식으로 이벤트 핸들러 등록!');
});
// 참조가 동일한 이벤트 핸들러를 중복 등록하면 하나의 핸들러만 등록됨
const handleMouseover = () => console.log('button mouseover');
$button.addEventListener('mouseover', handleMouseover);
$button.addEventListener('mouseover', handleMouseover);
</script>
```

> ### 이벤트 핸들러 제거 (Event Handler Removal)
EventTarget.prototype.removeEventListener 메서드를 통해 addEventListener 메서드로 등록한 이벤트 핸들러를 제거</br>
removeEventListener 메서드에 전달할 인수는 addEventListener 메서드와 동일하며, 전달한 인수가 일치하지 않을 경우 이벤트 핸들러는 제거되지 않음

```html
<button id="btn">클릭해보세요</button>
<script>
const $button = document.getElementById('btn');
const handleClick = () => alert('클릭했대요~');
// 이벤트 핸들러 등록
$button.addEventListener('click', handleClick);
// 이벤트 핸들러 제거
$button.removeEventListener('click', handleClick);
// 이벤트 핸들러 등록
// 등록한 이벤트 핸들러를 참조할 수 없으므로 제거할 수 없음
$button.addEventListener('mouseover', () => alert('마우스 올렸대요~'));
</script>
```

> ### 왜 사용해야 하는가?
1. **유연성**: 다양한 방법으로 이벤트 핸들러를 등록하고 제거할 수 있음
2. **재사용성**: 동일한 이벤트 핸들러를 여러 요소에 재사용할 수 있음
3. **유지보수 용이**: 이벤트 핸들러를 코드에서 쉽게 관리하고 유지보수할 수 있음

> ### 쉬운 요약
1. 이벤트 핸들러는 "이벤트가 발생했을 때 호출되는 함수"
    - HTML 어트리뷰트, 이벤트 핸들러 프로퍼티, addEventListener 메서드로 등록 가능
    - removeEventListener 메서드로 제거 가능

> ### 비유
1. 알람 설정
    - 이벤트 핸들러는 "알람을 설정하고 해제하는 과정"과 같음
    - 예: 특정 시간에 알람을 설정하고, 필요 없을 때 알람을 해제

2. 리모컨 버튼
    - 이벤트 핸들러는 "리모컨 버튼을 눌렀을 때 동작하는 기능"과 같음
    - 예: 리모컨 버튼을 눌렀을 때 TV가 켜지거나 꺼지는 동작

[뒤로](javascript.md)
