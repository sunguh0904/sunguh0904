## JavaScript Number Object
> ### Number 객체란?
Number 객체는 JavaScript에서 숫자를 다룰 때 유용한 프로퍼티와 메서드를 제공하는 표준 빌트인 객체</br>
주로 숫자 값을 생성하고, 숫자와 관련된 다양한 작업을 수행할 때 사용됨

> ### Number 객체의 주요 기능
1. Number 생성자 함수
    ```javascript
    // Number 인스턴스 생성
    const obj = new Number(); // 인수 전달하지 않을 경우 0을 할당
    console.log(obj); // 0

    const obj2 = new Number(1);
    console.log(obj2); // 1

    const obj3 = new Number('1');
    console.log(obj3); // 1

    const obj4 = new Number('number');
    console.log(obj4); // NaN
    ```

2. Number 프로퍼티
    - `Number.MAX_VALUE`: 자바스크립트에서 표현할 수 있는 가장 큰 양수 값
    - `Number.MIN_VALUE`: 자바스크립트에서 표현할 수 있는 가장 작은 양수 값
    - `Number.MAX_SAFE_INTEGER`: 자바스크립트에서 안전하게 표현할 수 있는 가장 큰 정수 값
    - `Number.MIN_SAFE_INTEGER`: 자바스크립트에서 안전하게 표현할 수 있는 가장 작은 정수 값
    - `Number.POSITIVE_INFINITY`: 양의 무한대를 나타내는 숫자 값
    - `Number.NEGATIVE_INFINITY`: 음의 무한대를 나타내는 숫자 값
    - `Number.NaN`: 숫자가 아님을 나타내는 숫자 값
    - `Number.EPSILON`: 부동 소수점으로 인해 발생하는 오차를 해결하기 위해 사용
    ```javascript
    console.log(Number.MAX_VALUE); // 1.7976931348623157e+308
    console.log(Number.MIN_VALUE); // 5e-324
    console.log(Number.MAX_SAFE_INTEGER); // 9007199254740991
    console.log(Number.MIN_SAFE_INTEGER); // -9007199254740991
    console.log(Number.POSITIVE_INFINITY); // Infinity
    console.log(Number.NEGATIVE_INFINITY); // -Infinity
    console.log(Number.NaN); // NaN
    console.log(Number.EPSILON); // 2.220446049250313e-16

    // 부동 소수점 오차 해결 예시
    console.log(0.1 + 0.2); // 0.30000000000000004
    console.log(0.1 + 0.2 === 0.3); // false
    console.log(isEqual(0.1 + 0.2, 0.3)); // true

    function isEqual(a, b) {
        return Math.abs(a - b) < Number.EPSILON;
    }
    ```

3. Number 메서드
    - `Number.isFinite`: 인수로 전달된 숫자 값이 정상적인 유한수인지 검사하여 결과를 불리언으로 반환
    - `Number.isInteger`: 인수로 전달된 숫자 값이 정수인지 검사하여 결과를 불리언으로 반환
    - `Number.isNaN`: 인수로 전달된 숫자 값이 NaN인지 검사하여 결과를 불리언으로 반환
    - `Number.isSafeInteger`: 인수로 전달된 숫자 값이 안전한 정수인지 검사하여 결과를 불리언으로 반환
    - `Number.prototype.toExponential`: 숫자를 지수 표기법으로 변환하여 문자열로 반환
    - `Number.prototype.toFixed`: 숫자를 반올림하여 문자열로 반환
    - `Number.prototype.toPrecision`: 인수로 전달받은 전체 자릿수까지 유효하도록 나머지 자릿수를 반올림하여 문자열로 반환
    - `Number.prototype.toString`: 숫자를 문자열로 변환하여 반환
    ```javascript
    console.log(Number.isFinite(10)); // true
    console.log(Number.isFinite(Infinity)); // false
    console.log(Number.isInteger(10)); // true
    console.log(Number.isInteger(10.1)); // false
    console.log(Number.isNaN(NaN)); // true
    console.log(Number.isSafeInteger(10)); // true
    console.log(Number.isSafeInteger(1000000000000000000000)); // false

    console.log((1.23456).toExponential()); // 1.23456e+0
    console.log((1.23456).toFixed(2)); // 1.23
    console.log((123.456).toPrecision(5)); // 123.46
    console.log((100).toString(2)); // 1100100
    ```

> ### 왜 사용해야 하는가?
1. **숫자 처리**: Number 객체를 사용하면 숫자와 관련된 다양한 작업을 쉽게 수행할 수 있음
2. **정확한 계산**: 부동 소수점 오차를 해결하고, 안전한 정수 범위 내에서 정확한 계산을 수행할 수 있음
3. **데이터 변환**: 숫자를 문자열로 변환하거나, 지수 표기법으로 변환하여 다양한 형식으로 데이터를 처리할 수 있음

> ### 쉬운 요약
1. Number 객체는 "숫자를 다룰 때 유용한 프로퍼티와 메서드를 제공하는 표준 빌트인 객체"
    - 주로 숫자 값을 생성하고, 숫자와 관련된 다양한 작업을 수행할 때 사용됨

2. 주요 기능: Number 생성자 함수, Number 프로퍼티, Number 메서드

> ### 비유
1. 계산기
    - Number 객체는 "다양한 기능을 제공하는 계산기"와 같음
    - 예: 계산기를 사용하여 다양한 계산을 수행하는 것처럼, Number 객체를 사용하여 숫자와 관련된 다양한 작업을 수행

2. 변환기
    - Number 객체는 "숫자를 다양한 형식으로 변환하는 변환기"와 같음
    - 예: 변환기를 사용하여 숫자를 문자열이나 지수 표기법으로 변환하는 것처럼, Number 객체를 사용하여 숫자를 다양한 형식으로 변환

[뒤로](javascript.md)
