# JavaScript Study Notes
> ### JavaScript란?
JavaScript는 웹 페이지의 동작을 제어하고, 사용자와 상호작용할 수 있는 기능을 제공하는 프로그래밍 언어</br>
주로 웹 페이지의 동적 콘텐츠를 생성하고, 이벤트를 처리하는 데 사용됨

> ### JavaScript의 주요 기능
1. 동적 콘텐츠 생성: HTML 요소를 동적으로 생성하고 조작
    ```javascript
    // 새로운 p 요소를 생성하고, 텍스트를 추가한 후, body에 추가
    const p = document.createElement('p');
    p.textContent = 'This is a dynamically created paragraph.';
    document.body.appendChild(p);
    ```

2. 이벤트 처리: 사용자 이벤트를 처리
    ```javascript
    // 버튼 클릭 이벤트를 처리하여 경고 메시지를 표시
    const button = document.querySelector('button');
    button.addEventListener('click', () => {
        alert('Button was clicked!');
    });
    ```

3. 데이터 검증: 폼 데이터를 검증
    ```javascript
    // 폼 제출 시 입력된 이메일 주소를 검증
    const form = document.querySelector('form');
    form.addEventListener('submit', (event) => {
        const email = form.elements['email'].value;
        if (!email.includes('@')) {
            alert('Please enter a valid email address.');
            event.preventDefault();
        }
    });
    ```

4. 비동기 통신: 서버와 비동기적으로 데이터를 주고받음
    ```javascript
    // Fetch API를 사용하여 서버에서 데이터를 가져옴
    fetch('https://api.example.com/data')
        .then(response => response.json())
        .then(data => {
            console.log(data);
        })
        .catch(error => {
            console.error('Error fetching data:', error);
        });
    ```

> ### 왜 사용해야 하는가?
1. **동적 콘텐츠 생성**: JavaScript를 사용하면 웹 페이지의 동적 콘텐츠를 쉽게 생성하고 조작할 수 있음
2. **이벤트 처리**: 사용자 이벤트를 처리하여 상호작용을 구현할 수 있음
3. **비동기 통신**: 서버와 비동기적으로 데이터를 주고받아 사용자 경험을 향상시킬 수 있음

> ### 쉬운 요약
1. JavaScript는 "웹 페이지의 동작을 제어하고, 사용자와 상호작용할 수 있는 프로그래밍 언어"
    - 주로 웹 페이지의 동적 콘텐츠를 생성하고, 이벤트를 처리하는 데 사용됨

2. 주요 기능: 동적 콘텐츠 생성, 이벤트 처리, 데이터 검증, 비동기 통신

> ### 비유
1. 리모컨
    - JavaScript는 "TV 리모컨"과 같음
    - 예: 리모컨을 사용하여 TV의 채널을 변경하고, 볼륨을 조절하는 것처럼, JavaScript로 웹 페이지의 동작을 제어

2. 요리사
    - JavaScript는 "요리사"와 같음
    - 예: 요리사가 재료를 조작하고, 요리를 완성하는 것처럼, JavaScript로 웹 페이지의 요소를 조작하고, 동작을 구현

## 추가 자료
1. [JavaScript Variables: 변수](Variables.md)
2. [JavaScript Operators: 연산자](Operators.md)

[뒤로](/README.md)
