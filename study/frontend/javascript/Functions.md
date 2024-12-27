## JavaScript Functions
> ### 함수란?
함수(Function)는 특정 작업을 수행하는 코드 블록</br>
주로 재사용 가능한 코드를 작성하고, 필요할 때 호출하여 실행하는 데 사용됨

> ### 함수 정의 방법
1. 함수 선언: `function` 키워드를 사용하여 함수 정의
    ```javascript
    // 함수 선언을 사용하여 함수 정의
    function greet(name) {
        console.log('Hello, ' + name);
    }

    // 함수 호출
    greet('John'); // Hello, John
    ```

2. 함수 표현식: 변수에 함수를 할당하여 함수 정의
    ```javascript
    // 함수 표현식을 사용하여 함수 정의
    const greet = function(name) {
        console.log('Hello, ' + name);
    };

    // 함수 호출
    greet('John'); // Hello, John
    ```

3. 화살표 함수: 간결한 문법으로 함수를 정의
    ```javascript
    // 화살표 함수를 사용하여 함수 정의
    const greet = (name) => {
        console.log('Hello, ' + name);
    };

    // 함수 호출
    greet('John'); // Hello, John
    ```

> ### 함수의 주요 특징
1. **매개변수**: 함수에 전달되는 입력 값
    ```javascript
    function add(a, b) {
        return a + b;
    }
    console.log(add(2, 3)); // 5
    ```

2. **반환 값**: 함수가 실행된 후 반환하는 값
    ```javascript
    function multiply(a, b) {
        return a * b;
    }
    console.log(multiply(2, 3)); // 6
    ```

3. **스코프**: 함수 내에서 정의된 변수는 함수 외부에서 접근할 수 없음
    ```javascript
    function example() {
        let x = 10;
        console.log(x); // 10
    }
    example();
    // console.log(x); // ReferenceError: x is not defined
    ```

> ### 왜 사용해야 하는가?
1. **코드 재사용**: 함수를 사용하면 동일한 코드를 여러 번 재사용할 수 있음
2. **가독성 향상**: 함수를 사용하여 코드를 모듈화하고, 가독성을 향상시킬 수 있음
3. **유지보수 용이**: 함수를 사용하여 코드를 분리하고, 유지보수를 용이하게 할 수 있음

> ### 쉬운 요약
1. 함수는 "특정 작업을 수행하는 코드 블록"
    - 주로 재사용 가능한 코드를 작성하고, 필요할 때 호출하여 실행하는 데 사용됨

2. 주요 특징: 매개변수, 반환 값, 스코프

> ### 비유
1. 요리 레시피
    - 함수는 "요리 레시피"와 같음
    - 예: 요리 레시피를 따라 요리를 만드는 것처럼, 함수를 호출하여 작업을 수행

2. 도구
    - 함수는 "특정 작업을 수행하는 도구"와 같음
    - 예: 도구를 사용하여 작업을 수행하는 것처럼, 함수를 호출하여 작업을 수행

[뒤로](javascript.md)
