## JavaScript Attributes
> ### 어트리뷰트 (attribute)
Element.prototype.attributes 프로퍼티로 모든 어트리뷰트 노드를 취득할 수 있음</br>
attributes 프로퍼티는 getter만 존재하는 읽기 전용 접근자 프로퍼티로 NameNodeMap 객체를 반환

```html
<label for="username">유저명</label>
<input type="text" id="username" value="user01">
```
```javascript
const attributes = document.getElementById('username').attributes;
console.log(attributes); // NodeNameMap 객체 반환
console.log(attributes.type.value); // 어트리뷰트 값 취득
console.log(attributes.id.value);
console.log(attributes.value.value);
```

Element.prototype.getAttribute/setAttribute 메서드를 사용하면 attributes 프로퍼티를 통하지 않고 요소 노드에서 메서드를 통해 직접 HTML 어트리뷰트 값을 취득하거나 변경할 수 있음

```javascript
const $input = document.getElementById('username');
const inputValue = $input.getAttribute('value'); // value 어트리뷰트 값 취득
console.log(inputValue);
$input.setAttribute('value', 'user02'); // value 어트리뷰트 값 변경
```

Element.prototype.hasAttribute(attributeName) 메서드를 사용하면 특정 HTML 어트리뷰트가 존재하는지 확인할 수 있음</br>
Element.prototype.removeAttribute(attributeName) 메서드를 사용하면 특정 HTML 어트리뷰트를 삭제할 수 있음

```html
<label for="nickname">닉네임</label>
<input type="text" id="nickname" value="JSMaster">
```
```javascript
const $nickname = document.getElementById('nickname');
console.log($nickname.hasAttribute('name')); // name 어트리뷰트를 가지고 있는지 확인
if ($nickname.hasAttribute('value')) {
    $nickname.removeAttribute('value'); // value 어트리뷰트가 있으면 삭제
}
console.log($nickname.hasAttribute('value')); // value 어트리뷰트를 가지고 있는지 확인
```

> ### 어트리뷰트와 프로퍼티 (attribute and property)
HTML 어트리뷰트: HTML 요소의 초기 상태를 지정하며 변하지 않음</br>
어트리뷰트 노드에서 관리되며 값을 얻거나 변경하려면 getAttribute/setAttribute 메서드를 사용</br>
DOM 프로퍼티: 사용자가 입력한 최신 상태를 관리</br>
사용자의 입력에 의한 상태 변화에 반응하여 언제나 최신 상태를 유지

```html
<label for="username">유저명</label>
<input type="text" id="username" value="user01">
<label for="nickname">닉네임</label>
<input type="text" id="nickname" value="JSBeginner">
```
```javascript
const $user = document.getElementById('username');
$user.oninput = () => {
    console.log('value 프로퍼티 값', $user.value);
    console.log('value 어트리뷰트 값', $user.getAttribute('value'));
};
const $nickname = document.getElementById('nickname');
$nickname.value = 'JSMaster'; // DOM 프로퍼티에 값을 할당하여 HTML 요소의 최신 상태를 변경
console.log('value 프로퍼티 값', $nickname.value);
console.log('value 어트리뷰트 값', $nickname.getAttribute('value'));
$nickname.id = 'nick'; // id는 사용자 입력에 의한 상태 변화와 관계 없는 어트리뷰트이므로 id 어트리뷰트와 id 프로퍼티는 항상 동일한 값으로 연동
console.log($nickname.id);
console.log($nickname.getAttribute('id'));
```

getAttribute 메서드로 취득한 어트리뷰트 값은 언제나 문자열</br>
하지만 DOM 프로퍼티로 취득한 최신 상태 값은 문자열이 아닐 수 있음</br>
checkbox 요소의 checked 어트리뷰트 값은 문자열이지만 checked 프로퍼티 값은 불리언 타입

```html
<label for="check">확인</label>
<input type="checkbox" id="check" checked>
```
```javascript
const $checkbox = document.querySelector('input[type=checkbox]');
console.log($checkbox.getAttribute('checked')); // getAttribute 메서드로 얻은 어트리뷰트 값은 문자열
console.log($checkbox.checked); // DOM 프로퍼티로 얻은 최신 상태 값은 불리언
```

> ### data 어트리뷰트와 dataset 어트리뷰트 (data attribute & dataset attribute)
data 어트리뷰트와 dataset 프로퍼티로 HTML 요소에 정의한 사용자 정의 어트리뷰트와 자바스크립트 간 데이터 교환이 가능</br>
data 어트리뷰트는 data- 접두사 다음에 임의의 이름을 붙여 사용</br>
HTMLElement.dataset 프로퍼티로 DOMStringMap 객체 반환 받으면 임의의 이름을 카멜 케이스로 변환한 프로퍼티를 가지고 있음

```html
<ul class="boardlist">
    <li data-board-id="13" data-category-id="1">망원 맛집 추천 부탁드려요!</li>
    <li data-board-id="15" data-category-id="2">한강 러닝 크루 구해요!</li>
    <li data-board-id="18" data-category-id="3">요즘 재태크 어떻게 하시나요?</li>
</ul>
```
```javascript
const boardlist = Array.from(document.querySelector('.boardlist').children);
boardlist.forEach(board => console.log(board.dataset)); // DOMStringMap 객체 반환 출력
const board = boardlist.find(board => board.dataset.categoryId === '1'); // categoryId가 '1'인 요소 노드를 취득
board.dataset.categoryId = '4'; // categoryId를 '4'로 변경
board.dataset.boardWriter = 'JS사랑해'; // 새로운 data 어트리뷰트 추가 가능
```

[뒤로](javascript.md)
