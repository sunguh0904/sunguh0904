## JavaScript Math Object
> ### Math 객체란?
Math 객체는 JavaScript에서 수학적인 상수와 함수를 위한 프로퍼티와 메서드를 제공하는 표준 빌트인 객체</br>
Math는 생성자 함수가 아니므로 정적 프로퍼티와 정적 메서드만 제공

> ### Math 객체의 주요 기능
1. Math 프로퍼티
    - `Math.PI`: 원주율 PI 값을 반환
    ```javascript
    console.log(Math.PI); // 3.141592653589793
    ```

2. Math 메서드
    - `Math.abs`: 인수로 전달된 숫자의 절대값을 반환
    ```javascript
    console.log(Math.abs(-10)); // 10
    console.log(Math.abs('-10')); // 10
    console.log(Math.abs('')); // 0
    console.log(Math.abs([])); // 0
    console.log(Math.abs(null)); // 0
    console.log(Math.abs(undefined)); // NaN
    console.log(Math.abs({})); // NaN
    console.log(Math.abs('math')); // NaN
    ```

    - `Math.round`: 인수로 전달된 숫자의 소수점 이하를 반올림한 정수를 반환
    ```javascript
    console.log(Math.round(10.1)); // 10
    console.log(Math.round(10.9)); // 11
    console.log(Math.round(-10.1)); // -10
    console.log(Math.round(-10.9)); // -11
    console.log(Math.round(10)); // 10
    console.log(Math.round()); // NaN
    ```

    - `Math.ceil`: 인수로 전달된 숫자의 소수점 이하를 올림한 정수를 반환
    ```javascript
    console.log(Math.ceil(10.1)); // 11
    console.log(Math.ceil(10.9)); // 11
    console.log(Math.ceil(-10.1)); // -10
    console.log(Math.ceil(-10.9)); // -10
    console.log(Math.ceil(10)); // 10
    console.log(Math.ceil()); // NaN
    ```

    - `Math.floor`: 인수로 전달된 숫자의 소수점 이하를 내림한 정수를 반환
    ```javascript
    console.log(Math.floor(10.1)); // 10
    console.log(Math.floor(10.9)); // 10
    console.log(Math.floor(-10.1)); // -11
    console.log(Math.floor(-10.9)); // -11
    console.log(Math.floor(10)); // 10
    console.log(Math.floor()); // NaN
    ```

    - `Math.sqrt`: 인수로 전달된 숫자의 제곱근을 반환
    ```javascript
    console.log(Math.sqrt(4)); // 2
    console.log(Math.sqrt(-4)); // NaN
    console.log(Math.sqrt(2)); // 1.4142135623730951
    console.log(Math.sqrt(1)); // 1
    console.log(Math.sqrt(0)); // 0
    console.log(Math.sqrt()); // NaN
    ```

    - `Math.random`: 임의의 난수(0에서 1 미만의 실수) 반환
    ```javascript
    console.log(Math.random());
    // 1~100 범위의 난수 추출
    const random = Math.floor((Math.random() * 100) + 1);
    console.log(random);
    ```

    - `Math.pow`: 첫 번째 인수를 밑으로 두 번째 인수를 지수로 거듭제곱한 결과 반환
    ```javascript
    console.log(Math.pow(2, 2)); // 4
    console.log(Math.pow(2, -2)); // 0.25
    console.log(Math.pow(2)); // NaN

    // ES7에서 도입된 지수 연산자를 사용할 수 있음
    console.log(2 ** 2); // 4
    console.log(2 ** -2); // 0.25
    ```

    - `Math.max`: 전달받은 인수 중 가장 큰 수를 반환
    ```javascript
    console.log(Math.max(10)); // 10
    console.log(Math.max(10, 20)); // 20
    console.log(Math.max(10, 20, 30)); // 30
    console.log(Math.max()); // -Infinity
    ```

    - `Math.min`: 전달받은 인수 중 가장 작은 수를 반환
    ```javascript
    console.log(Math.min(10)); // 10
    console.log(Math.min(10, 20)); // 10
    console.log(Math.min(10, 20, 30)); // 10
    console.log(Math.min()); // Infinity
    ```

> ### 왜 사용해야 하는가?
1. **수학적 계산**: Math 객체를 사용하면 다양한 수학적 계산을 쉽게 수행할 수 있음
2. **정확한 결과**: Math 객체의 메서드를 사용하여 정확한 계산 결과를 얻을 수 있음
3. **편리한 사용**: Math 객체는 정적 프로퍼티와 메서드를 제공하여 편리하게 사용할 수 있음

> ### 쉬운 요약
1. Math 객체는 "수학적인 상수와 함수를 위한 프로퍼티와 메서드를 제공하는 표준 빌트인 객체"
    - Math는 생성자 함수가 아니므로 정적 프로퍼티와 정적 메서드만 제공

2. 주요 기능: Math 프로퍼티, Math 메서드

> ### 비유
1. 계산기
    - Math 객체는 "다양한 수학적 계산을 수행하는 계산기"와 같음
    - 예: 계산기를 사용하여 다양한 수학적 계산을 수행하는 것처럼, Math 객체를 사용하여 수학적 계산을 수행

2. 도구 상자
    - Math 객체는 "다양한 수학적 도구가 들어있는 도구 상자"와 같음
    - 예: 도구 상자에서 필요한 도구를 꺼내어 작업을 수행하는 것처럼, Math 객체의 메서드를 사용하여 수학적 작업을 수행

[뒤로](javascript.md)
