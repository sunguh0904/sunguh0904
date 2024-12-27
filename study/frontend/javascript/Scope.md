## JavaScript Scope
> ### 스코프란?
스코프(Scope)는 변수나 함수가 접근할 수 있는 유효 범위를 의미</br>
주로 변수의 가시성과 생명 주기를 결정하는 데 사용됨

> ### 스코프의 종류
1. 전역 스코프: 코드 어디서든 접근할 수 있는 범위
    ```javascript
    // 전역 변수 선언
    var globalVar = 'I am global';

    function showGlobalVar() {
        console.log(globalVar); // I am global
    }

    showGlobalVar();
    console.log(globalVar); // I am global
    ```

2. 함수 스코프: 함수 내에서만 접근할 수 있는 범위
    ```javascript
    function showLocalVar() {
        var localVar = 'I am local';
        console.log(localVar); // I am local
    }

    showLocalVar();
    // console.log(localVar); // ReferenceError: localVar is not defined
    ```

3. 블록 스코프: 블록 내에서만 접근할 수 있는 범위 (let, const)
    ```javascript
    if (true) {
        let blockVar = 'I am block scoped';
        console.log(blockVar); // I am block scoped
    }

    // console.log(blockVar); // ReferenceError: blockVar is not defined
    ```

> ### 스코프 체인
스코프 체인은 내부 스코프에서 외부 스코프로 접근할 수 있는 구조를 의미
    ```javascript
    var globalVar = 'I am global';

    function outerFunction() {
        var outerVar = 'I am outer';

        function innerFunction() {
            var innerVar = 'I am inner';
            console.log(globalVar); // I am global
            console.log(outerVar); // I am outer
            console.log(innerVar); // I am inner
        }

        innerFunction();
    }

    outerFunction();
    ```

> ### 왜 사용해야 하는가?
1. **변수 가시성 관리**: 스코프를 사용하면 변수의 가시성을 관리할 수 있음
2. **코드 구조화**: 스코프를 사용하여 코드를 구조화하고, 가독성을 향상시킬 수 있음
3. **변수 충돌 방지**: 스코프를 사용하여 변수 충돌을 방지할 수 있음

> ### 쉬운 요약
1. 스코프는 "변수나 함수가 접근할 수 있는 유효 범위"
    - 주로 변수의 가시성과 생명 주기를 결정하는 데 사용됨

2. 주요 스코프 종류: 전역 스코프, 함수 스코프, 블록 스코프

> ### 비유
1. 방
    - 스코프는 "방"과 같음
    - 예: 방 안에서만 사용할 수 있는 물건처럼, 특정 스코프 내에서만 접근할 수 있는 변수

2. 회사 조직도
    - 스코프 체인은 "회사 조직도"와 같음
    - 예: 하위 부서에서 상위 부서로 접근할 수 있는 구조처럼, 내부 스코프에서 외부 스코프로 접근

[뒤로](javascript.md)
