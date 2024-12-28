## JavaScript Node Modification
> ### innerHTML
Element.prototype.innerHTML 프로퍼티는 setter와 getter 모두 존재하는 접근자 프로퍼티로 요소 노드의 HTML 마크업을 취득하거나 변경</br>
textContent 프로퍼티는 HTML 마크업을 무시하고 텍스트만 반환하지만 innerHTML 프로퍼티는 HTML 마크업이 포함된 문자열을 그대로 반환

```html
<div id="area">태그 엘리먼트의 값을 읽거나, 변경할 때 <span>innerHTML</span> 속성을 사용함</div>
```
```javascript
const $area = document.getElementById('area');
// 읽어온 요소가 가지는 값 출력
console.log($area.innerHTML);
// 노드 추가
$area.innerHTML += '값 추가';
// 노드 교체
$area.innerHTML = "<h1>innerHTML</h1>속성으로 값 변경";
// 노드 삭제
$area.innerHTML = '';
```

innerHTML 프로퍼티를 사용한 DOM 조작은 구현이 간단하고 직관적이라는 장점이 있음</br>
하지만 사용자로부터 입력받은 데이터를 그대로 innerHTML 프로퍼티에 할당하는 것은 XSS(Cross-Site Scripting Attacks)에 취약하므로 위험</br>
HTML 마크업 내에 자바스크립트 악성 코드가 포함되어 있다면 파싱 과정에서 그대로 실행될 가능성이 있음

```javascript
// 에러 이벤트를 강제로 발생시켜서 자바스크립트 코드가 실행되도록 함
$area.innerHTML = `<img src='x' onerror='alert("메롱메롱~")'>`;
```

innerHTML 프로퍼티에 HTML 마크업 문자열을 할당하는 경우 요소 노드의 모든 자식 노드를 제거하고 할당한 HTML 마크업 문자열을 파싱하여 DOM을 변경</br>
또한, 새로운 요소를 삽입할 때 삽입될 위치를 지정할 수 없다는 단점도 있음

```html
<ul id="list">
    <li class="coffee">커피</li>
</ul>
```
```javascript
const $list = document.getElementById('list');
// 노드 추가
$list.innerHTML += "<li class='coke'>콜라</li>";
```

> ### insertAdjacentHTML
Element.prototype.insertAdjacentHTML(position, DOMString) 메서드는 기존 요소를 제거하지 않으면서 위치를 지정해 새로운 요소를 삽입</br>
첫 번째 인수로 전달할 수 있는 문자열은 ‘beforebegin’, ‘afterbegin’, ‘beforeend’, ’afterend’의 4가지

```html
<div id="area">
    insertAdjacentHTML 메소드 사용 테스트
</div>
```
```javascript
const $area = document.getElementById('area');
$area.insertAdjacentHTML('beforebegin', '<h1>beforebegin 테스트</h1>');
$area.insertAdjacentHTML('afterbegin', '<h1>afterbegin 테스트</h1>');
$area.insertAdjacentHTML('beforeend', '<h1>beforeend 테스트</h1>');
$area.insertAdjacentHTML('afterend', '<h1>afterend 테스트</h1>');
```

> ### 노드 생성 및 추가 (node create & append)
1. Document.prototype.createElement(tagName): 인수로 전달받은 태그 이름에 해당하는 요소 노드를 생성하여 반환
2. Document.prototype.createTextNode(text): 인수로 전달받은 텍스트 값으로 텍스트 노드를 생성하여 반환
3. Node.prototype.appendChild(childNode): 인수로 전달받은 노드를 appendChild 메서드를 호출한 노드의 마지막 자식 노드로 추가

```html
<ul id="drink">
    <li>커피</li>
</ul>
```
```javascript
const $drink = document.getElementById('drink');
// 요소 노드 생성
const $li = document.createElement('li');
// 텍스트 노드 생성
$li.textContent = '콜라';
// $li 요소 노드를 $drink 요소 노드의 마지막 자식 노드로 추가
$drink.appendChild($li);
```

복수의 노드를 생성하여 추가하는 상황에서 DOM의 reflow, repaint 횟수를 줄이는 것이 좋음</br>
DocumentFragment 노드는 자식 노드들의 부모 노드로서 별도의 서브 DOM을 구성하여 기존 DOM에 추가하기 위한 용도로 사용할 수 있음

```html
<ul id="food">
    <li>김치찌개</li>
</ul>
```
```javascript
const $food = document.getElementById('food');
const $fragment = document.createDocumentFragment();
['된장찌개', '고등어구이', '순대국'].forEach(text => {
    const $li = document.createElement('li');
    $li.textContent = text;
    $fragment.appendChild($li);
});
$food.appendChild($fragment);
```

> ### 노드 삽입 및 이동 (node insert & move)
1. Node.prototype.appendChild(childNode): 인수로 전달받은 노드를 appendChild 메서드를 호출한 노드의 마지막 자식 노드로 추가
2. Node.prototype.insertBefore(newNode, childNode): 첫 번째 인수로 전달받은 노드를 두 번째 인수로 전달받은 노드 앞에 삽입

```html
<ul id="drink">
    <li>커피</li>
</ul>
```
```javascript
const $drink = document.getElementById('drink');
const $li1 = document.createElement('li');
$li1.textContent = '콜라';
$drink.appendChild($li1);
const $li2 = document.createElement('li');
$li2.textContent = '우유';
$drink.insertBefore($li2, $drink.lastElementChild);
```

DOM에 이미 존재하는 노드를 appendChild, insertBefore 메서드를 사용하여 DOM에 다시 추가하면 현재 위치에서 노드를 제거하고 새로운 위치에 노드를 추가하는 노드 이동이 발생

```html
<ul id="food">
    <li>파스타</li>
    <li>피자</li>
</ul>
```
```javascript
const $food = document.getElementById('food');
const [$pasta, $pizza] = $food.children;
$drink.appendChild($pasta);
$drink.insertBefore($pizza, $pasta);
```

> ### 노드 복사, 교체 및 제거 (node copy, replace & remove)
1. Node.prototype.cloneNode([deep: true | false]): 노드의 사본을 생성하여 반환
2. Node.prototype.replaceChild(newChild, oldChild): 자신을 호출한 노드의 자식 노드인 oldChild 노드를 newChild 노드로 교체
3. Node.prototype.removeChild(child): child 매개변수에 인수로 전달한 노드를 DOM에서 삭제

```html
<ul class="copy">
    ul 영역
    <li>li 영역</li>
</ul>
```
```javascript
const $ul = document.querySelector(".copy");
const $li = $ul.firstElementChild;
const $shallowClone = $li.cloneNode(false);
const $deepClone = $ul.cloneNode(true);
$ul.appendChild($shallowClone);
$ul.appendChild($deepClone);
```

```html
<ul id="drink">
    <li>커피</li>
    <li>사이다</li>
</ul>
```
```javascript
const $drink = document.getElementById('drink');
const $coffee = $drink.firstElementChild;
const $newChild = document.createElement('li');
$newChild.textContent = '콜라';
$drink.replaceChild($newChild, $coffee);
```

```html
<ul id="food">
    <li>파스타</li>
    <li>피자</li>
</ul>
```
```javascript
const $food = document.getElementById('food');
$food.removeChild($food.lastElementChild);
```

[뒤로](javascript.md)
