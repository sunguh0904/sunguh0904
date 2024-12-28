## JavaScript Array Higher-Order Functions
> ### 고차 함수란?
고차 함수(Higher-Order Function)는 함수를 인수로 전달받거나 함수를 반환하는 함수</br>
주로 배열의 요소를 처리하고 변환하는 데 사용됨

> ### 주요 배열 고차 함수
1. `Array.prototype.sort`
    - 배열을 정렬 기준으로 정렬
    ```javascript
    let numbers = [];
    for (let i = 0; i < 10; i++) {
        numbers[i] = Math.floor(Math.random() * 100) + 1;
    }
    console.log(`정렬 전 numbers : ${numbers}`);
    numbers.sort();
    console.log(`정렬 후 numbers : ${numbers}`);

    // 숫자 오름차순 정렬
    numbers.sort((a, b) => a - b);
    // 숫자 내림차순 정렬
    numbers.sort((a, b) => b - a);
    ```

2. `Array.prototype.forEach`
    - 배열의 각 요소에 대해 함수를 실행
    ```javascript
    const numbers = [1, 2, 3, 4, 5];
    numbers.forEach(item => console.log(item * 10));
    ```

3. `Array.prototype.map`
    - 배열의 각 요소에 대해 함수를 실행하고, 그 결과로 새로운 배열을 반환
    ```javascript
    const types = [true, 1, 'text'].map(item => typeof item);
    console.log(`types : ${types}`); // boolean,number,string

    const lengths = ['apple', 'banana', 'cat', 'dog', 'egg'].map(item => item.length);
    console.log(`lengths : ${lengths}`); // 5,6,3,3,3
    ```

4. `Array.prototype.filter`
    - 배열의 각 요소에 대해 함수를 실행하고, 그 결과가 true인 요소로만 구성된 새로운 배열을 반환
    ```javascript
    const numbers = [1, 2, 3, 4, 5];
    const odds = numbers.filter(item => item % 2);
    console.log(odds); // [1, 3, 5]
    ```

5. `Array.prototype.reduce`
    - 배열을 순회하며 각 요소에 대해 이전의 콜백 함수 실행 반환값을 전달하여 콜백 함수를 실행하고 그 결과를 반환
    ```javascript
    const numbers = [1, 2, 3, 4, 5];

    // 합산
    const sum = numbers.reduce((previousValue, currentValue) => previousValue + currentValue);
    console.log(`sum : ${sum}`); // 15

    // 최대값
    const max = numbers.reduce((pre, cur) => (pre > cur ? pre : cur));
    console.log(`max : ${max}`); // 5
    ```

6. `Array.prototype.some`
    - 배열 내 일부 요소가 콜백 함수의 테스트를 통과하는지 확인하여 그 결과를 boolean으로 반환
    ```javascript
    let result = [1, 5, 3, 2, 4].some(item => item > 10);
    console.log(`result : ${result}`); // false

    result = [1, 5, 3, 2, 4].some(item => item > 3);
    console.log(`result : ${result}`); // true

    result = ['apple', 'banana', 'cat', 'dog'].some(item => item === 'egg');
    console.log(`result : ${result}`); // false

    result = ['apple', 'banana', 'cat', 'dog'].some(item => item === 'dog');
    console.log(`result : ${result}`); // true
    ```

7. `Array.prototype.every`
    - 배열 내 모든 요소가 콜백 함수의 테스트를 통과하는지 확인하여 그 결과를 boolean으로 반환
    ```javascript
    let result = [1, 5, 3, 2, 4].every(item => item > 3);
    console.log(`result : ${result}`); // false

    result = [1, 5, 3, 2, 4].every(item => item > 0);
    console.log(`result : ${result}`); // true
    ```

8. `Array.prototype.find`, `Array.prototype.findIndex`
    - `find`: 배열을 순회하며 각 요소에 대해 인자로 주어진 콜백 함수를 실행하여 그 결과가 참인 첫 번째 요소를 반환
    - `findIndex`: 배열을 순회하며 각 요소에 대해 인자로 주어진 콜백 함수를 실행하여 그 결과가 참인 첫 번째 요소의 인덱스를 반환
    ```javascript
    const students = [
        { name: '유관순', score: 90 },
        { name: '홍길동', score: 80 },
        { name: '장보고', score: 70 }
    ];

    let result = students.find(item => item.name === '유관순');
    console.log(result); // { name: '유관순', score: 90 }

    result = students.findIndex(item => item.name === '유관순');
    console.log(result); // 0

    result = students.find(item => item.name === '신사임당');
    console.log(result); // undefined

    result = students.findIndex(item => item.name === '신사임당');
    console.log(result); // -1

    // filter를 이용하여 일치하는 여러 요소를 반환
    result = students.filter(item => item.score >= 60);
    console.log(result); // [{ name: '유관순', score: 90 }, { name: '홍길동', score: 80 }, { name: '장보고', score: 70 }]
    ```

> ### 왜 사용해야 하는가?
1. **데이터 처리**: 고차 함수를 사용하면 배열의 데이터를 효율적으로 처리할 수 있음
2. **코드 간결화**: 고차 함수를 사용하여 코드를 간결하게 작성할 수 있음
3. **다양한 기능 제공**: 고차 함수는 다양한 기능을 제공하여 데이터를 효율적으로 처리할 수 있음

> ### 쉬운 요약
1. 고차 함수는 "함수를 인수로 전달받거나 함수를 반환하는 함수"
    - 주로 배열의 요소를 처리하고 변환하는 데 사용됨

2. 주요 함수: `sort`, `forEach`, `map`, `filter`, `reduce`, `some`, `every`, `find`, `findIndex`

> ### 비유
1. 도구 상자
    - 고차 함수는 "다양한 도구가 들어있는 도구 상자"와 같음
    - 예: 도구 상자에서 필요한 도구를 꺼내어 작업을 수행하는 것처럼, 고차 함수를 사용하여 배열을 조작

2. 요리 도구
    - 고차 함수는 "요리를 위한 다양한 도구"와 같음
    - 예: 요리를 할 때 다양한 도구를 사용하여 재료를 준비하고 요리를 완성하는 것처럼, 고차 함수를 사용하여 데이터를 처리

[뒤로](javascript.md)
