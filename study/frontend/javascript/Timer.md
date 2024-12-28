## JavaScript Timer
> ### 타이머 메소드 (timer method)
JavaScript에서는 타이머를 사용하여 일정 시간 후에 코드를 실행하거나, 일정 시간 간격으로 코드를 반복 실행할 수 있음

> ### setTimeout
setTimeout 함수는 두 번째 인수로 전달받은 시간(ms, 1/1000초)으로 단 한 번 동작하는 타이머를 생성</br>
이후 타이머가 만료되면 첫 번째 인수로 전달 받은 콜백 함수가 호출됨</br>
콜백 함수에 전달해야 하는 인수가 존재하는 경우 세 번째 이후의 인수로 전달할 수 있음

```javascript
setTimeout(() => console.log('1초 지났지롱~'), 1000);
setTimeout((msg) => console.log(`1..2..3.. ${msg}`), 3000, '기다렸어?');
```

> ### clearTimeout
setTimeout 함수는 생성된 타이머를 식별할 수 있는 고유한 타이머 id를 반환</br>
반환한 id를 clearTimeout 함수의 인수로 전달하여 타이머를 취소할 수 있음

```javascript
const timerId = setTimeout(() => console.log('나는 곧 취소될거야'), 2000);
console.log(timerId); // 브라우저 환경에서는 숫자, Node.js 환경의 경우 객체
clearTimeout(timerId);
```

> ### setInterval
setInterval 함수는 두 번째 인수로 전달받은 시간(ms, 1/1000초)으로 반복 동작하는 타이머를 생성</br>
이후 타이머가 만료될 때마다 첫 번째 인수로 전달 받은 콜백 함수가 반복 호출됨</br>
이는 타이머가 취소될 때까지 계속됨</br>
콜백 함수에 전달해야 하는 인수가 존재하는 경우 세 번째 이후의 인수로 전달할 수 있음

```javascript
let count = 1;
const timerId = setInterval(() => {
    console.log(count);
    if (count++ === 5) clearInterval(timerId);
}, 1000);
```

> ### clearInterval
setInterval 함수는 생성된 타이머를 식별할 수 있는 고유한 타이머 id를 반환</br>
반환한 id를 clearInterval 함수의 인수로 전달하여 타이머를 취소할 수 있음

```javascript
const intervalId = setInterval(() => console.log('반복 실행'), 1000);
setTimeout(() => clearInterval(intervalId), 5000); // 5초 후에 타이머 취소
```

> ### 왜 사용해야 하는가?
1. **비동기 작업 처리**: 일정 시간 후에 코드를 실행하거나, 일정 시간 간격으로 코드를 반복 실행할 수 있음
2. **유연성**: 타이머를 사용하여 다양한 비동기 작업을 처리할 수 있음
3. **제어 가능성**: 타이머 id를 사용하여 타이머를 취소하거나 제어할 수 있음

> ### 쉬운 요약
1. setTimeout은 "일정 시간 후에 코드를 실행하는 타이머"
2. setInterval은 "일정 시간 간격으로 코드를 반복 실행하는 타이머"
3. clearTimeout과 clearInterval은 "타이머를 취소하는 메소드"

> ### 비유
1. 알람 시계
    - setTimeout은 "알람 시계에서 특정 시간에 울리는 알람"과 같음
    - 예: 특정 시간에 알람이 울리도록 설정

2. 주기적인 알람
    - setInterval은 "주기적으로 울리는 알람"과 같음
    - 예: 매 시간마다 알람이 울리도록 설정

3. 알람 취소
    - clearTimeout과 clearInterval은 "설정된 알람을 취소하는 것"과 같음
    - 예: 알람이 울리기 전에 알람을 취소

[뒤로](javascript.md)
