## JavaScript Event Samples
> ### 마우스 이벤트 (mouse event)
마우스 이벤트 종류
- mousedown/mouseup
- mouseover/mouseout
- mousemove
- click
- contextmenu

```html
<button>클릭해보세요</button>
<div class="area"></div>
```
```javascript
const $btn = document.querySelector("button");
const $area = document.querySelector(".area");
// event.button
// 0 : 왼쪽, 1 : 가운데, 2 : 오른쪽
$btn.onmousedown = (e) => {
    $area.insertAdjacentHTML('beforeend', 'mousedown button=' + e.button + "<br>");
};
$btn.onmouseup = (e) => {
    $area.insertAdjacentHTML('beforeend', 'mouseup button=' + e.button + "<br>");
};
$btn.onmouseover = (e) => {
    $area.insertAdjacentHTML('beforeend', 'mouseover button=' + e.button + "<br>");
};
$btn.onmouseout = (e) => {
    $area.insertAdjacentHTML('beforeend', 'mouseout button=' + e.button + "<br>");
};
$btn.onclick = (e) => {
    $area.insertAdjacentHTML('beforeend', 'click button=' + e.button + "<br>");
};
$btn.ondblclick = (e) => {
    $area.insertAdjacentHTML('beforeend', 'dblclick button=' + e.button + "<br>");
};
$btn.oncontextmenu = (e) => {
    $area.insertAdjacentHTML('beforeend', 'contextmenu button=' + e.button + "<br>");
};
```

> ### 선택, 복사 막기 (prevent select copy)
mousedown, mousemove 이벤트가 발생할 때 나타나는 브라우저 기본 동작을 막으면 글씨 선택을 막을 수 있음</br>
copy 이벤트가 발생할 때 나타나는 브라우저 기본 동작을 막아 복사를 막을 수도 있음</br>
브라우저 기본 동작을 막는 방법은 이벤트 객체의 preventDefault 메서드를 호출하는 방법과 이벤트 핸들러 함수 반환 값을 false로 지정하는 것이 있음

```html
<span>
    이 영역은 드래그 해도, 또는 더블 클릭해도 선택 되지 않도록 합니다
</span>
<div>
    이 편지는 영국에서 최초로 시작되어 일년에 한 바퀴 돌면서
    받는 사람에게 행운을 주었고 지금은 당신에게로 옮겨진 이 편지는
    4일 안에 당신 곁을 떠나야 합니다. 이 편지를 포함해서 7통을
    행운이 필요한 사람에게 보내 주셔야 합니다. 복사는 안됩니다.
</div>
```
```javascript
const $span = document.querySelector('span');
$span.onmousedown = (e) => e.preventDefault();
$span.onmousemove = (e) => e.preventDefault();
const $div = document.querySelector('div');
$div.oncopy = () => {
    alert('복사 불가능입니다!');
    return false;
}
```

> ### 키보드 이벤트 (keyboard event)
키보드 이벤트 종류
- keydown
- keyup

키보드 이벤트 속성
- event.key : 문자
- event.code : 물리적인 키 코드

Ex. 소문자 a를 입력하면 event.key=a event.code=KeyA 대문자 A를 입력하면 event.key=A event.code=KeyA

```html
<input type="text" placeholder="아무 키나 입력하세요">
<div class="area"></div>
```
```javascript
const $message = document.querySelector("input[type=text]");
const $area = document.querySelector(".area");
$message.onkeydown = (e) => {
    $area.insertAdjacentHTML('beforeend', 'keydown key=' + e.key + ", code=" + e.code + "<br>");
};
$message.onkeyup = (e) => {
    $area.insertAdjacentHTML('beforeend', 'keyup key=' + e.key + ", code=" + e.code + "<br>");
};
```

> ### 사용자 입력 양식 이벤트 (input event)
폼 요소 값 다루기
- input, textarea : input.value 또는 input.checked(checkbox 또는 radio)
- select.options : option 하위 요소들을 담고 있는 컬렉션
- select.value : 현재 선택 된 option 값
- select.selectedIndex : 현재 선택 된 option의 번호(인덱스)

```html
<form name="memberjoin">
    <label for="username">이름</label>
    <input type="text" name="username" id="username" value="홍길동">
    <br><br>

    <label>성별</label>
    <input type="radio" name="gender" id="male" value="m" checked><label for="male">남자</label>
    <input type="radio" name="gender" id="female" value="f"><label for="female">여자</label>

    <br><br>
    <label>나이</label>
    <select id="age" name="age">
        <option value="10">10대 이하</option>
        <option value="20">20대</option>
        <option value="30">30대</option>
        <option value="40">40대</option>
        <option value="50">50대</option>
        <option value="60">60대 이상</option>
    </select>
    <br><br>
    <label>자기소개</label>
    <textarea name="introduce" id="introduce" rows="5" cols="30" style="resize:none;">저를 소개합니다!</textarea>
    <span>0</span>/5000자
    <br><br>
    <input type="submit" value="제출">
</form>
```
```javascript
// 폼 취득
// 문서 내 모든 form들을 HTMLCollection 타입으로 반환
console.log(document.forms);
console.log(document.forms.memberjoin); // name 속성 값
console.log(document.forms[0]); // 인덱스 값
const $form = document.forms.memberjoin;
// 요소 취득
// form 내 사용자 입력 양식을 HTMLFormControlsCollection 타입으로 반환
console.log($form.elements);
console.log($form.elements.username);
const $username = $form.username;
console.log(`$form.username.value : ${$username.value}`);
$username.value = '유관순';
const $gender = $form.gender;
console.log(`$form.gender[1].checked : ${$gender[1].checked}`);
$gender[1].checked = true;
const $age = $form.age;
console.log($age.options);
$age.options[2].selected = true;
age.selectedIndex = 3;
age.value = '50';
const $introduce = $form.introduce;
console.log($introduce.value);
$introduce.value = 'value';
// $introduce.textContent = 'textContent';
```

focus : 사용자가 폼 요소를 클릭하거나 tab 키를 눌러 요소로 이동 했을 때 발생하는 이벤트</br>
blur : 사용자가 다른 곳을 클릭하거나 tab 키를 눌러 다음 폼 필드로 이동했을 때 발생하는 이벤트</br>
또한 focus, blur 메소드로 요소에 포커스를 주거나 제거할 수 있음

```javascript
$username.onfocus = (e) => {
    e.target.classList.toggle('lightgray');
};
$username.onblur = (e) => {
    e.target.classList.toggle('lightgray');
};
```

focus 이벤트는 해당 입력 필드에서만 동작하고 버블링 되지 않음</br>
버블링이 필요하다면 focusin, focusout 이벤트를 사용

```javascript
// $form.addEventListener('focus', (e) => e.target.classList.add('focused'));
// $form.addEventListener('blur', (e) => e.target.classList.remove('focused'));
$form.addEventListener('focusin', (e) => e.target.classList.add('focused'));
$form.addEventListener('focusout', (e) => e.target.classList.remove('focused'));
```

change 이벤트는 요소 변경이 끝나면 발생하는 이벤트</br>
select/checkbox/radio의 경우 선택 값이 변경 된 직후 이벤트가 발생하지만 텍스트 입력 요소인 경우 변경 후 포커스를 잃었을 때 이벤트가 발생

```javascript
$age.addEventListener('change', () => alert('age change!'));
$introduce.addEventListener('change', () => alert('introduce change!'));
```

input 이벤트는 키보드 이벤트와 달리 어떤 방법으로든 값을 변경할 때 발생</br>
예를 들어 마우스를 사용하여 글자를 붙여 넣거나 음성 인식 기능을 사용해서 글자를 입력할 때도 반응

```javascript
$introduce.addEventListener('input', (e) => {
    let len = e.target.value.trim().length;
    $form.querySelector('span').textContent = len;
});
```

> ### 폼 제출 이벤트 (form submit event)
submit은 폼을 제출할 때 동작하는 이벤트로 폼을 서버로 전송하기 전 내용을 검증하여 폼 전송을 취소할 때 사용</br>
폼을 전송하는 방법으로는 (1) input type="submit" 또는 input type="image" 클릭 (2) input 필드에서 Enter 키 누르기가 있음

```html
<form method="GET" action="https://search.naver.com/search.naver" name="search">
    <input type="text" name="query" placeholder="검색할 키워드를 입력하세요">
    <button type="submit">네이버 검색하기</button>
</form>
```
```javascript
const $form = document.forms.search;
$form.onsubmit = function() {
    let keyword = this.querySelector('input[name=query]').value;
    if (!keyword) {
        alert('검색어를 입력하지 않았습니다!');
        return false;
    }
};
```

> ### 왜 사용해야 하는가?
1. **다양한 이벤트 처리**: 다양한 이벤트를 처리하여 사용자와 상호작용할 수 있음
2. **유연성**: 이벤트를 통해 다양한 동작을 구현할 수 있음
3. **유지보수 용이**: 이벤트 핸들러를 코드에서 쉽게 관리하고 유지보수할 수 있음

> ### 쉬운 요약
1. 이벤트 샘플은 "다양한 이벤트를 처리하는 예제"
    - 마우스 이벤트, 키보드 이벤트, 사용자 입력 양식 이벤트, 폼 제출 이벤트 등을 포함

> ### 비유
1. 리모컨
    - 이벤트 샘플은 "리모컨 버튼을 눌렀을 때 동작하는 기능"과 같음
    - 예: 리모컨 버튼을 눌렀을 때 TV가 켜지거나 꺼지는 동작

2. 요리사
    - 이벤트 샘플은 "요리사가 재료를 조작하고 요리를 완성하는 과정"과 같음
    - 예: 재료를 추가하고, 제거하고, 조리하는 과정

[뒤로](javascript.md)
