## JavaScript Operators
> ### 연산자란?
연산자(Operator)는 값을 연산하고, 결과를 반환하는 데 사용되는 기호나 키워드</br>
주로 산술 연산, 비교 연산, 논리 연산 등을 수행하는 데 사용됨

> ### 주요 연산자 종류
1. 산술 연산자: 숫자 값을 연산
    ```javascript
    let a = 10;
    let b = 5;
    console.log(a + b); // 덧셈: 15
    console.log(a - b); // 뺄셈: 5
    console.log(a * b); // 곱셈: 50
    console.log(a / b); // 나눗셈: 2
    console.log(a % b); // 나머지: 0
    ```

2. 비교 연산자: 두 값을 비교
    ```javascript
    let x = 10;
    let y = 5;
    console.log(x == y); // 동등: false
    console.log(x != y); // 부등: true
    console.log(x > y); // 크다: true
    console.log(x < y); // 작다: false
    console.log(x >= y); // 크거나 같다: true
    console.log(x <= y); // 작거나 같다: false
    ```

3. 논리 연산자: 논리 값을 연산
    ```javascript
    let p = true;
    let q = false;
    console.log(p && q); // 논리 AND: false
    console.log(p || q); // 논리 OR: true
    console.log(!p); // 논리 NOT: false
    ```

4. 할당 연산자: 값을 변수에 할당
    ```javascript
    let z = 10;
    z += 5; // z = z + 5: 15
    z -= 3; // z = z - 3: 12
    z *= 2; // z = z * 2: 24
    z /= 4; // z = z / 4: 6
    z %= 3; // z = z % 3: 0
    ```

5. 삼항 연산자: 조건에 따라 값을 선택
    ```javascript
    let age = 20;
    let isAdult = (age >= 18) ? 'Yes' : 'No';
    console.log(isAdult); // Yes
    ```

6. Nullish Coalescing 연산자 (ES11): null 또는 undefined인 경우에만 오른쪽 피연산자를 반환
    ```javascript
    let foo = null ?? 'default';
    console.log(foo); // 'default'

    let bar = 0 ?? 'default';
    console.log(bar); // 0
    ```

> ### 왜 사용해야 하는가?
1. **값 연산**: 연산자를 사용하면 값을 연산하고, 결과를 반환할 수 있음
2. **조건 처리**: 비교 연산자와 논리 연산자를 사용하여 조건을 처리할 수 있음
3. **코드 간결화**: 삼항 연산자와 Nullish Coalescing 연산자를 사용하여 조건문을 간결하게 작성할 수 있음

> ### 쉬운 요약
1. 연산자는 "값을 연산하고, 결과를 반환하는 기호나 키워드"
    - 주로 산술 연산, 비교 연산, 논리 연산 등을 수행하는 데 사용됨

2. 주요 연산자: 산술 연산자, 비교 연산자, 논리 연산자, 할당 연산자, 삼항 연산자, Nullish Coalescing 연산자

> ### 비유
1. 계산기
    - 연산자는 "계산기"와 같음
    - 예: 계산기를 사용하여 숫자를 더하고, 빼고, 곱하고, 나누는 것처럼, 연산자를 사용하여 값을 연산

2. 교통 신호
    - 연산자는 "교통 신호"와 같음
    - 예: 교통 신호를 사용하여 차량의 이동을 제어하는 것처럼, 연산자를 사용하여 값의 조건을 제어

[뒤로](javascript.md)
