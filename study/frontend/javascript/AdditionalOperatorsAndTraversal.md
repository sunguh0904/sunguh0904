## JavaScript Additional Operators and Traversal
> ### 추가 연산자와 순회란?
추가 연산자와 순회는 JavaScript에서 데이터를 조작하고 탐색하는 데 사용되는 다양한 연산자와 메서드</br>
주로 객체와 배열의 속성 및 요소를 조작하고, 데이터를 순회하는 데 사용됨

> ### 주요 추가 연산자
1. 옵셔널 체이닝 연산자 `?.`: 객체의 속성에 안전하게 접근
    ```javascript
    const user = {
        name: 'John',
        address: {
            city: 'New York'
        }
    };

    // 옵셔널 체이닝을 사용하여 안전하게 속성에 접근
    console.log(user?.address?.city); // New York
    console.log(user?.contact?.phone); // undefined
    ```

2. Nullish Coalescing 연산자 `??`: null 또는 undefined인 경우에만 오른쪽 피연산자를 반환
    ```javascript
    let foo = null ?? 'default';
    console.log(foo); // 'default'

    let bar = 0 ?? 'default';
    console.log(bar); // 0
    ```

> ### 주요 순회 메서드
1. `for...in`: 객체의 열거 가능한 속성을 순회
    ```javascript
    const person = {
        name: 'John',
        age: 30,
        job: 'Developer'
    };

    // for...in을 사용하여 객체의 속성을 순회
    for (let key in person) {
        console.log(`${key}: ${person[key]}`);
    }
    ```

2. `for...of`: 배열이나 이터러블 객체의 요소를 순회
    ```javascript
    const numbers = [1, 2, 3, 4, 5];

    // for...of를 사용하여 배열의 요소를 순회
    for (let number of numbers) {
        console.log(number);
    }
    ```

3. `Object.keys()`, `Object.values()`, `Object.entries()`: 객체의 키, 값, 키-값 쌍을 배열로 반환
    ```javascript
    const person = {
        name: 'John',
        age: 30,
        job: 'Developer'
    };

    // 객체의 키를 배열로 반환
    console.log(Object.keys(person)); // ['name', 'age', 'job']

    // 객체의 값을 배열로 반환
    console.log(Object.values(person)); // ['John', 30, 'Developer']

    // 객체의 키-값 쌍을 배열로 반환
    console.log(Object.entries(person)); // [['name', 'John'], ['age', 30], ['job', 'Developer']]
    ```

> ### 왜 사용해야 하는가?
1. **안전한 속성 접근**: 옵셔널 체이닝 연산자를 사용하여 객체의 속성에 안전하게 접근할 수 있음
2. **효율적인 데이터 처리**: 다양한 순회 메서드를 사용하여 객체와 배열의 데이터를 효율적으로 처리할 수 있음
3. **코드 간결화**: 추가 연산자와 순회 메서드를 사용하여 코드를 간결하게 작성할 수 있음

> ### 쉬운 요약
1. 추가 연산자와 순회는 "JavaScript에서 데이터를 조작하고 탐색하는 데 사용되는 다양한 연산자와 메서드"
    - 주로 객체와 배열의 속성 및 요소를 조작하고, 데이터를 순회하는 데 사용됨

2. 주요 연산자: 옵셔널 체이닝 연산자 `?.`, Nullish Coalescing 연산자 `??`
3. 주요 순회 메서드: `for...in`, `for...of`, `Object.keys()`, `Object.values()`, `Object.entries()`

> ### 비유
1. 안전한 탐색
    - 옵셔널 체이닝 연산자는 "안전한 탐색"과 같음
    - 예: 위험한 지역을 피하면서 안전하게 탐색하는 것처럼, 객체의 속성에 안전하게 접근

2. 지도
    - 순회 메서드는 "지도를 사용하여 지역을 탐색"하는 것과 같음
    - 예: 지도를 사용하여 지역의 각 부분을 탐색하는 것처럼, 객체와 배열의 각 요소를 순회

[뒤로](javascript.md)
