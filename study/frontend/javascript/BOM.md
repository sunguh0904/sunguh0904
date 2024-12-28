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

> ### location 객체
location 객체는 현재 문서의 URL 정보를 제공하고 제어할 수 있는 객체

```javascript
// 현재 URL 정보 출력
console.log(window.location.href);
// 새로운 URL로 이동
window.location.href = 'https://www.example.com';
```

> ### navigator 객체
navigator 객체는 브라우저의 정보를 제공하는 객체

```javascript
// 브라우저의 사용자 에이전트 정보 출력
console.log(window.navigator.userAgent);
// 브라우저의 언어 정보 출력
console.log(window.navigator.language);
```

> ### screen 객체
screen 객체는 사용자의 화면 정보를 제공하는 객체

```javascript
// 화면의 너비와 높이 출력
console.log(window.screen.width);
console.log(window.screen.height);
```

> ### history 객체
history 객체는 브라우저의 세션 기록을 제어할 수 있는 객체

```javascript
// 뒤로 가기
window.history.back();
// 앞으로 가기
window.history.forward();
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
