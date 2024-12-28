## JavaScript Arrays
> ### 배열이란?
배열(Array)은 여러 개의 값을 하나의 변수에 저장할 수 있는 데이터 구조</br>
주로 동일한 타입의 데이터를 순차적으로 저장하고, 인덱스를 사용하여 접근할 때 사용됨

> ### 배열의 주요 특징
1. 배열 생성: 배열 리터럴 또는 Array 생성자를 사용하여 배열 생성
    ```javascript
    // 배열 리터럴을 사용하여 배열 생성
    const fruits = ['Apple', 'Banana', 'Cherry'];

    // Array 생성자를 사용하여 배열 생성
    const numbers = new Array(1, 2, 3, 4, 5);
    ```

2. 배열 요소 접근: 인덱스를 사용하여 배열 요소에 접근
    ```javascript
    const fruits = ['Apple', 'Banana', 'Cherry'];
    console.log(fruits[0]); // Apple
    console.log(fruits[1]); // Banana
    console.log(fruits[2]); // Cherry
    ```

3. 배열 길이: 배열의 길이를 확인
    ```javascript
    const fruits = ['Apple', 'Banana', 'Cherry'];
    console.log(fruits.length); // 3
    ```

4. 배열 메서드: 배열 조작을 위한 다양한 메서드 제공
    ```javascript
    const fruits = ['Apple', 'Banana', 'Cherry'];

    // 배열에 요소 추가
    fruits.push('Date');
    console.log(fruits); // ['Apple', 'Banana', 'Cherry', 'Date']

    // 배열에서 요소 제거
    fruits.pop();
    console.log(fruits); // ['Apple', 'Banana', 'Cherry']

    // 배열의 일부를 추출
    const citrus = fruits.slice(1, 2);
    console.log(citrus); // ['Banana']
    ```

> ### 왜 사용해야 하는가?
1. **데이터 저장**: 배열을 사용하면 여러 개의 값을 하나의 변수에 저장할 수 있음
2. **데이터 접근**: 인덱스를 사용하여 배열의 각 요소에 쉽게 접근할 수 있음
3. **데이터 조작**: 배열 메서드를 사용하여 데이터를 쉽게 조작할 수 있음

> ### 쉬운 요약
1. 배열은 "여러 개의 값을 하나의 변수에 저장할 수 있는 데이터 구조"
    - 주로 동일한 타입의 데이터를 순차적으로 저장하고, 인덱스를 사용하여 접근할 때 사용됨

2. 주요 특징: 배열 생성, 배열 요소 접근, 배열 길이, 배열 메서드

> ### 비유
1. 책장
    - 배열은 "책장"과 같음
    - 예: 책장에 여러 권의 책을 순서대로 저장하고, 인덱스를 사용하여 특정 책에 접근

2. 리스트
    - 배열은 "리스트"와 같음
    - 예: 리스트에 여러 항목을 순서대로 저장하고, 인덱스를 사용하여 특정 항목에 접근

[뒤로](javascript.md)
