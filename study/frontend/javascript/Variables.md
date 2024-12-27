## JavaScript Variables
> ### 변수란?
변수(Variable)는 데이터를 저장하고 참조하기 위해 사용되는 이름이 붙은 저장소</br>
주로 값을 저장하고, 그 값을 나중에 참조하거나 변경할 때 사용됨

> ### 변수 선언 방법
1. `var`: 변수를 선언하는 오래된 방식
    ```javascript
    // var 키워드를 사용하여 변수 선언
    var name = 'John';
    console.log(name); // John
    ```

2. `let`: 변수를 선언하는 현대적인 방식 (블록 스코프를 가짐)
    ```javascript
    // let 키워드를 사용하여 변수 선언
    let age = 30;
    console.log(age); // 30
    ```

3. `const`: 상수를 선언하는 방식 (값을 변경할 수 없음)
    ```javascript
    // const 키워드를 사용하여 상수 선언
    const pi = 3.14;
    console.log(pi); // 3.14
    ```

> ### 변수의 주요 특징
1. **스코프**: 변수의 유효 범위
    - `var`는 함수 스코프를 가짐
    - `let`과 `const`는 블록 스코프를 가짐
    ```javascript
    function example() {
        var x = 10;
        if (true) {
            let y = 20;
            const z = 30;
            console.log(x); // 10
            console.log(y); // 20
            console.log(z); // 30
        }
        console.log(x); // 10
        // console.log(y); // ReferenceError: y is not defined
        // console.log(z); // ReferenceError: z is not defined
    }
    example();
    ```

2. **재할당**: 변수에 새로운 값을 할당
    - `var`와 `let`은 재할당이 가능
    - `const`는 재할당이 불가능
    ```javascript
    var name = 'John';
    name = 'Doe'; // 재할당 가능
    console.log(name); // Doe

    let age = 30;
    age = 31; // 재할당 가능
    console.log(age); // 31

    const pi = 3.14;
    // pi = 3.14159; // TypeError: Assignment to constant variable.
    ```

> ### 왜 사용해야 하는가?
1. **데이터 저장**: 변수를 사용하면 데이터를 저장하고 참조할 수 있음
2. **코드 가독성 향상**: 변수 이름을 통해 코드의 의미를 명확히 할 수 있음
3. **값의 재사용**: 변수를 사용하여 값을 재사용할 수 있음

> ### 쉬운 요약
1. 변수는 "데이터를 저장하고 참조하기 위해 사용되는 이름이 붙은 저장소"
    - 주로 값을 저장하고, 그 값을 나중에 참조하거나 변경할 때 사용됨

2. 주요 변수 선언 방법: `var`, `let`, `const`

> ### 비유
1. 상자
    - 변수는 "데이터를 저장하는 상자"와 같음
    - 예: 상자에 물건을 넣고, 나중에 그 물건을 꺼내 사용하는 것처럼, 변수에 값을 저장하고 참조

2. 이름표
    - 변수는 "데이터에 붙이는 이름표"와 같음
    - 예: 이름표를 붙여서 물건을 구분하는 것처럼, 변수 이름을 통해 값을 구분하고 참조

[뒤로](javascript.md)
