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
1. [Variables: "변수로 데이터 저장하기"](Variables.md)
2. [Operators: "연산자로 값 계산하기"](Operators.md)
3. [Object Literals: "객체 리터럴로 데이터 구조화하기"](ObjectLiterals.md)
4. [Properties: "속성으로 객체 데이터 관리하기"](Properties.md)
5. [Additional Operators and Traversal: "추가 연산자와 순회로 데이터 탐색하기"](AdditionalOperatorsAndTraversal.md)
6. [Functions: "함수로 코드 재사용하기"](Functions.md)
7. [Scope: "스코프로 변수 가시성 관리하기"](Scope.md)
8. [Object Constructor Function: "객체 생성자 함수로 객체 생성하기"](ObjectConstructorFunction.md)
9. [Prototype: "프로토타입으로 객체 상속 구현하기"](Prototype.md)
10. [Strict Mode: "Strict Mode로 안전한 코드 작성하기"](StrictMode.md)
11. [Array: "배열로 여러 값 저장하기"](Array.md)
12. [Array Methods: "배열 메소드로 데이터 조작하기"](ArrayMethods.md)
13. [Array Higher-Order Functions: "배열 고차 함수로 데이터 처리하기"](ArrayHigherOrderFunctions.md)
14. [Global Properties: "전역 프로퍼티로 표준화된 값 사용하기"](GlobalProperties.md)
15. [Global Functions: "전역 함수로 데이터 처리하기"](GlobalFunctions.md)
16. [Number: "숫자 객체로 다양한 작업 수행하기"](Number.md)
17. [Math: "수학적 계산을 위한 Math 객체 사용하기"](Math.md)
18. [Date: "날짜와 시간을 위한 Date 객체 사용하기"](Date.md)

[뒤로](/README.md)
