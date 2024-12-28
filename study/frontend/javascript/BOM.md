## JavaScript Browser Object Model (BOM)
> ### BOM이란?
BOM (Browser Object Model)은 브라우저와 관련된 객체와 메서드를 제공하여 브라우저 창을 제어할 수 있게 해주는 모델</br>
주로 브라우저 창, 위치, 내비게이터, 화면, 히스토리 등을 제어하는 데 사용됨

> ### window 객체
브라우저 환경에서 자바스크립트가 돌아가는 플랫폼은 호스트(host)라고 불림</br>
호스트 환경이 웹 브라우저일 때 사용할 수 있는 기능은 개괄적으로 아래와 같음
- window
- DOM (document, …)
- BOM (location, navigator, screen, history, …)
- JavaScript (Object, Array, Function, …)

최상단의 window 객체는 자바스크립트 코드의 전역 객체이자 브라우저 창(browser window)을 대변하고 이를 제어할 수 있는 메서드를 제공</br>
window 객체는 전역 객체이므로 메서드 호출 시 생략할 수 있음

```javascript
// alert 메서드는 window 객체의 메서드이므로 window를 생략할 수 있음
alert('Hello, BOM!');
```

> ### window.open
window.open(url, name, params) 메서드는 새 창을 열 수 있음

- url: 새 창에 로드할 URL
- name: 새 창의 이름으로 해당 이름을 가진 창이 이미 있으면 그 안에서 열리고, 그렇지 않으면 새 창이 열림
- params: 새 창의 설정을 쉼표로 구분하여 문자열로 전달

```html
<button id="btn1">새로운 창 열기</button>
<button id="btn2">새로운 창 열기</button>
```
```javascript
document.getElementById('btn1').onclick = () => window.open('https://www.google.com', 'popup1', 'width=1080, height=800');
document.getElementById('btn2').onclick = () => window.open('https://www.naver.com', 'popup1');
```

> ### window.alert
window.alert(message) 메서드는 확인 버튼을 가지며 메시지를 지정할 수 있는 경고 대화 상자를 띄움

```javascript
window.alert('alert창입니다!');
```

> ### window.confirm
window.confirm(message) 메서드는 확인과 취소 두 버튼을 가지며 메시지를 지정할 수 있는 모달 대화 상자를 띄움</br>
반환 값은 확인을 누를 시 true, 취소를 누르거나 ESC 키를 누르면 false

```javascript
const answer = window.confirm('계속하시겠습니까?');
if (answer) {
    console.log('잘 선택하셨어요! 가보자고요~');
} else {
    console.log('아쉽네요... 다음에 또 만나요~');
}
```

> ### window.prompt
window.prompt(message, default) 메서드는 사용자가 텍스트를 입력할 수 있도록 안내하는 선택적 메시지를 갖고 있는 대화 상자를 띄움</br>
default: 텍스트 입력 필드에 기본으로 채워넣을 문자열</br>
반환 값은 확인을 누를 시 사용자가 입력한 문자열이며 취소를 누르거나 ESC 키를 누르면 null

```javascript
const likeNumber = window.prompt('좋아하는 숫자를 입력하세요', 7);
if (likeNumber) {
    console.log(`당신이 좋아하는 숫자는 ${likeNumber}이군요`);
} else {
    console.log('값을 입력하지 않으셨군요');
}
```

> ### location 객체
location 객체는 현재 문서의 URL 정보를 제공하고 제어할 수 있는 객체

```html
<button id="btn1">새 페이지로 이동하기</button>
<button id="btn2">새 페이지로 이동하기</button>
<button id="btn3">새 페이지로 이동하기</button>
<button id="btn4">새 페이지로 이동하기(뒤로 가기 불가)</button>
<button id="btn5">서버로부터 현재 페이지 리로드하기</button>
<button id="btn6">서버로부터 현재 페이지 리로드하기</button>
<button id="btn7">서버로부터 현재 페이지 리로드하기</button>
```
```javascript
document.getElementById('btn1').onclick = () => location.assign("https://www.google.com");
document.getElementById('btn2').onclick = () => location = "https://www.google.com";
document.getElementById('btn3').onclick = () => location.href = "https://www.google.com";
document.getElementById('btn4').onclick = () => location.replace("https://www.google.com");
document.getElementById('btn5').onclick = () => location.reload();
document.getElementById('btn6').onclick = () => location = location;
document.getElementById('btn7').onclick = () => location.href = location.href;
```

> ### navigator 객체
navigator 객체는 브라우저와 운영체제에 대한 정보를 제공하는 객체

```javascript
for (prop in navigator) {
    console.log(`${prop} : ${navigator[prop]}`);
}
console.log(navigator.userAgent);
console.log(navigator.platform);
```

> ### screen 객체
screen 객체는 웹 브라우저 화면이 아닌 운영체제 화면의 속성을 가지는 객체

```javascript
for (prop in screen) {
    console.log(`${prop} : ${screen[prop]}`);
}
```

> ### history 객체
history 객체는 브라우저의 세션 기록을 제어할 수 있는 객체

```html
<button id="btn1">뒤로 가기</button>
<button id="btn2">앞으로 가기</button>
<input type="number" name="page">
<button id="btn3">입력한 만큼 이동하기</button>
```
```javascript
for (prop in history) {
    console.log(`${prop} : ${history[prop]}`);
}
document.getElementById('btn1').onclick = () => history.back();
document.getElementById('btn2').onclick = () => history.forward();
document.getElementById('btn3').onclick = function() {
    let page = document.querySelector('input[name=page]').value;
    history.go(page);
};
```

> ### 왜 사용해야 하는가?
1. **브라우저 제어**: BOM을 사용하면 브라우저 창, 위치, 내비게이터, 화면, 히스토리 등을 제어할 수 있음
2. **정보 제공**: BOM을 사용하면 브라우저와 관련된 다양한 정보를 얻을 수 있음
3. **유연성**: BOM을 사용하여 브라우저와 상호작용하는 다양한 기능을 구현할 수 있음

> ### 쉬운 요약
1. BOM은 "브라우저와 관련된 객체와 메서드를 제공하여 브라우저 창을 제어하는 모델"
    - window, location, navigator, screen, history 객체 등을 포함

2. 브라우저 창, 위치, 내비게이터, 화면, 히스토리 등을 제어하고 정보를 제공

> ### 비유
1. 리모컨
    - BOM은 "TV 리모컨"과 같음
    - 예: 리모컨을 사용하여 TV의 채널을 변경하고, 볼륨을 조절하는 것처럼, BOM을 사용하여 브라우저 창을 제어

2. 지도
    - BOM은 "지도에서 특정 위치를 찾고 이동하는 과정"과 같음
    - 예: 지도를 사용하여 특정 위치를 찾고, 이동 경로를 설정

[뒤로](javascript.md)
