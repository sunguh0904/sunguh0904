## JavaScript Global Properties
> ### 빌트인 전역 프로퍼티란?
빌트인 전역 프로퍼티는 JavaScript에서 전역 객체의 프로퍼티로, 어디서든 접근할 수 있는 값</br>
주로 무한대, 숫자가 아님(NaN), 정의되지 않음(undefined)을 나타내는 값이 포함됨

> ### 주요 빌트인 전역 프로퍼티
1. `Infinity`
    - 무한대를 나타내는 숫자 값
    ```javascript
    // 전역 프로퍼티는 global을 생략하고 참조할 수 있음
    console.log(global.Infinity === Infinity); // true

    // 양의 무한대
    console.log(10 / 0); // Infinity

    // 음의 무한대
    console.log(-10 / 0); // -Infinity

    console.log(typeof Infinity); // number
    ```

2. `NaN`
    - 숫자가 아님(Not a Number)을 나타내는 숫자 값
    - `Number.NaN` 프로퍼티와 같음
    ```javascript
    console.log(global.NaN); // NaN
    console.log(Number('abc')); // NaN
    console.log(10 * 'abc'); // NaN
    console.log(typeof NaN); // number
    ```

3. `undefined`
    - 원시 타입 undefined를 나타내는 값
    ```javascript
    console.log(global.undefined); // undefined

    let nothing;
    console.log(nothing); // undefined

    console.log(typeof undefined); // undefined
    ```

> ### 왜 사용해야 하는가?
1. **전역 접근성**: 빌트인 전역 프로퍼티는 어디서든 접근할 수 있어 편리함
2. **표준화된 값**: 무한대, NaN, undefined와 같은 표준화된 값을 제공하여 일관성을 유지할 수 있음
3. **디버깅 용이**: 코드에서 예상치 못한 값을 쉽게 확인하고 디버깅할 수 있음

> ### 쉬운 요약
1. 빌트인 전역 프로퍼티는 "어디서든 접근할 수 있는 전역 객체의 프로퍼티"
    - 주로 무한대, 숫자가 아님(NaN), 정의되지 않음(undefined)을 나타내는 값이 포함됨

2. 주요 프로퍼티: `Infinity`, `NaN`, `undefined`

> ### 비유
1. 공용 자원
    - 빌트인 전역 프로퍼티는 "모두가 접근할 수 있는 공용 자원"과 같음
    - 예: 공용 자원을 누구나 사용할 수 있는 것처럼, 전역 프로퍼티를 어디서든 사용할 수 있음

2. 표준 규격
    - 빌트인 전역 프로퍼티는 "표준 규격"과 같음
    - 예: 표준 규격을 사용하여 일관성을 유지하는 것처럼, 전역 프로퍼티를 사용하여 일관성을 유지

[뒤로](javascript.md)
