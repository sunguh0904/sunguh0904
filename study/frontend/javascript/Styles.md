## JavaScript Styles
> ### 인라인 스타일 (inline style)
HTMLElement.prototype.style 프로퍼티는 setter와 getter가 모두 존재하는 접근자 프로퍼티로 요소 노드의 인라인 스타일을 취득하거나 추가 또는 변경</br>
HTMLElement.prototype.style 프로퍼티는 CSSStyleDeclaration 타입의 객체를 반환하며, 이 프로퍼티에 값을 할당하면 해당 CSS 프로퍼티가 인라인 스타일로 HTML 요소에 추가되거나 변경됨

```html
<div style="color: white;">AREA</div>
```
```javascript
const $area = document.querySelector('div');
// 인라인 스타일 취득 - CSSStyleDeclaration 타입의 객체 반환
console.log($area.style);
// 인라인 스타일 추가
$area.style.width = '100px';
$area.style.height = '100px';
$area.style.backgroundColor = 'lightgray'; // 마침표 표기법
// $area.style['background-color'] = 'lightgray'; // 대괄호 표기법
```

> ### className과 classList
class 어트리뷰트에 대응하는 DOM 프로퍼티는 class가 아니라 className, classList</br>
Element.prototype.className 프로퍼티는 setter와 getter 모두 존재하는 접근자 프로퍼티로 요소 노드의 className 프로퍼티를 참조하면 class 어트리뷰트의 값을 문자열로 반환하고, 요소 노드의 className 프로퍼티에 문자열을 할당하면 class 어트리뷰트 값을 할당한 문자열로 변경</br>
Element.prototype.classList 프로퍼티는 class 어트리뷰트의 정보를 담은 DOMTokenList 객체를 반환

```html
<style>
.area {
    width: 100px;
    height: 100px;
    border: 1px solid black;
}
.circle { border-radius: 50%; }
.lightgray { background: lightgray; }
.yellow { background: yellow; }
</style>
<div class='area'></div>
```
```javascript
const $area = document.querySelector('.area');
console.log($area.className); // 문자열 반환
// 클래스명을 덮어쓰게 되어 .area가 제거됨
// $area.className = 'circle';
console.log($area.classList); // DOMTokenList 객체 반환
// add(...className), remove(...className) 으로 class 어트리뷰트에 값 추가 제거를 할 수 있음
$area.classList.add('circle');
$area.classList.add('lightgray');
// item(index)는 인수로 전달한 인덱스에 해당하는 클래스를 class 어트리뷰트에서 반환
console.log($area.classList.item(0));
console.log($area.classList.item(1));
console.log($area.classList.item(2));
// contains(className)은 인수로 전달한 문자열과 일치하는 클래스가 class 어트리뷰트에 포함되어 있는지 확인
console.log($area.classList.contains('circle'));
console.log($area.classList.contains('yellow'));
// replace(oldClassName, newClassName)는 첫 번째 인수로 전달한 문자열을 두 번째 인수로 전달한 문자열로 변경
$area.classList.replace('lightgray', 'yellow');
// toggle(className)은 class 어트리뷰트에 인수로 전달한 문자열과 일치하는 클래스가 존재하면 제거하고 존재하지 않으면 추가
$area.classList.toggle('yellow'); // 제거
$area.classList.toggle('yellow'); // 추가
$area.classList.remove('yellow'); // 제거
```

> ### 왜 사용해야 하는가?
1. **유연성**: 다양한 방법으로 요소의 스타일을 조작할 수 있음
2. **효율성**: 인라인 스타일, className, classList 등을 사용하여 효율적으로 스타일을 변경할 수 있음
3. **유지보수 용이**: 스타일 조작을 코드에서 쉽게 관리하고 유지보수할 수 있음

> ### 쉬운 요약
1. 스타일 조작은 "요소의 스타일을 변경하는 과정"
    - 인라인 스타일, className, classList 등을 사용

> ### 비유
1. 옷 갈아입기
    - 스타일 조작은 "옷을 갈아입는 과정"과 같음
    - 예: 옷을 입고 벗고, 스타일을 변경

2. 페인트칠
    - 스타일 조작은 "벽에 페인트칠을 하는 과정"과 같음
    - 예: 벽의 색상을 변경하고, 새로운 색상을 추가

[뒤로](javascript.md)
