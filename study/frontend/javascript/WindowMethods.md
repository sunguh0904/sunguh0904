## JavaScript Window Methods
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

> ### 왜 사용해야 하는가?
1. **사용자 상호작용**: 다양한 대화 상자를 통해 사용자와 상호작용할 수 있음
2. **유연성**: 새 창을 열거나, 경고, 확인, 입력 대화 상자를 통해 다양한 기능을 구현할 수 있음
3. **정보 제공**: 사용자에게 정보를 제공하고, 입력을 받을 수 있음

> ### 쉬운 요약
1. window.open은 "새 창을 여는 메서드"
2. window.alert는 "경고 대화 상자를 띄우는 메서드"
3. window.confirm은 "확인과 취소 버튼을 가지는 모달 대화 상자를 띄우는 메서드"
4. window.prompt는 "사용자가 텍스트를 입력할 수 있는 대화 상자를 띄우는 메서드"

> ### 비유
1. 새 창 열기
    - window.open은 "새로운 문을 여는 것"과 같음
    - 예: 새로운 문을 열어 다른 방으로 이동

2. 경고
    - window.alert는 "경고 알림을 보내는 것"과 같음
    - 예: 경고 알림을 통해 사용자에게 중요한 정보를 전달

3. 확인
    - window.confirm은 "사용자에게 확인을 요청하는 것"과 같음
    - 예: 사용자가 동의하거나 취소할 수 있는 선택지를 제공

4. 입력
    - window.prompt는 "사용자에게 입력을 요청하는 것"과 같음
    - 예: 사용자가 정보를 입력할 수 있는 창을 제공

[뒤로](javascript.md)
