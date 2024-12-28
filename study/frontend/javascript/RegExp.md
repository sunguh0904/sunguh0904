## JavaScript RegExp
> ### 정규 표현식이란?
정규 표현식(Regular expression)은 일정한 패턴을 가진 문자열의 집합을 표현하기 위해 사용하는 형식 언어</br>
주로 문자열을 대상으로 한 패턴 매칭 기능을 제공하여 비밀번호 패턴 확인, 전화번호 유효성 확인 등의 기능에서 활용

> ### RegExp 객체의 주요 기능
1. 정규 표현식 생성
    ```javascript
    const target = 'JavaScript'; // 검색 대상

    // 정규 표현식 리터럴 - /pattern/플래그
    let regexp = /j/i; // 패턴: j, 플래그: i (대소문자 구별 없이)

    // RegExp 생성자 함수 - new RegExp(pattern[, flag])
    regexp = new RegExp('j', 'i');
    regexp = new RegExp(/j/, 'i');
    regexp = new RegExp(/j/i); // ES6부터 가능한 표현

    // test 메서드 - target 문자열에 대해 정규 표현식 regexp의 패턴을 검색하여 매칭 결과를 불리언으로 반환
    console.log(regexp.test(target));
    ```

2. RegExp 메서드
    - `RegExp.prototype.exec`: 인수로 전달받은 문자열에 대해 정규 표현식의 패턴을 검색하여 매칭 결과를 배열로 반환
    ```javascript
    const target = 'Java JavaScript';
    console.log(/va/.exec(target)); // [ 'va', index: 2, input: 'Java JavaScript', groups: undefined ]
    console.log(/va/g.exec(target)); // [ 'va', index: 2, input: 'Java JavaScript', groups: undefined ]
    console.log(/hello/.exec(target)); // null
    ```

    - `RegExp.prototype.test`: 인수로 전달받은 문자열에 대해 정규 표현식의 패턴을 검색하여 매칭 결과를 불리언으로 반환
    ```javascript
    const target = 'Java JavaScript';
    console.log(/va/.test(target)); // true
    console.log(/hello/.test(target)); // false
    ```

    - `String.prototype.match`: 대상 문자열과 인수로 전달 받은 정규 표현식과의 매칭 결과를 배열로 반환
    ```javascript
    const target = 'Java JavaScript';
    console.log(target.match(/va/)); // [ 'va', index: 2, input: 'Java JavaScript', groups: undefined ]
    console.log(target.match(/va/g)); // [ 'va', 'va' ]
    console.log(target.match(/hello/)); // null
    ```

    - 이외에 정규 표현식을 사용하는 메서드: `String.prototype.replace`, `String.prototype.search`, `String.prototype.split` 등이 있음

3. 플래그와 패턴
    - 플래그 문자
        - `i` (ignore case): 대소문자를 구별하지 않고 패턴 검색
        - `g` (Global): 대상 문자열 내에서 패턴과 일치하는 모든 문자열을 전역 검색
    ```javascript
    let target = 'Java JavaScript';
    console.log(target.match(/VA/)); // null
    console.log(target.match(/VA/i)); // [ 'va', index: 2, input: 'Java JavaScript', groups: undefined ]
    console.log(target.match(/VA/ig)); // [ 'va', 'va' ]
    ```

    - 패턴
        - `.`: 임의의 문자열
        ```javascript
        target = 'abcdefg';
        console.log(target.match(/../g)); // [ 'ab', 'cd', 'ef' ]
        ```

        - `{m,n}`: 최소 m번, 최대 n번 반복되는 문자열 (반복 검색)
        ```javascript
        target = 'a aa aaa b bb bbb ab aab abb';
        console.log(target.match(/a{2,3}/g)); // [ 'aa', 'aaa', 'aa' ]
        console.log(target.match(/b{2}/g)); // [ 'bb', 'bb', 'bb' ]
        console.log(target.match(/b{3,}/g)); // [ 'bbb' ]
        ```

        - `+`: 앞선 패턴이 최소 한 번 이상 반복되는 문자열 (반복 검색)
        ```javascript
        target = 'a aa aaa b bb bbb ab aab abb';
        console.log(target.match(/b+/g)); // [ 'b', 'bb', 'bbb', 'b', 'b', 'bb' ]
        ```

        - `?`: 앞선 패턴이 최대 한 번(0번 포함) 반복되는 문자열 (반복 검색)
        ```javascript
        target = 'soul seoul';
        console.log(target.match(/se?oul/g)); // [ 'soul', 'seoul' ]
        ```

        - `|`: or
        ```javascript
        target = 'aa bb cc dd 123 456 _@';
        console.log(target.match(/a|b/g)); // [ 'a', 'a', 'b', 'b' ]
        console.log(target.match(/a+|b+/g)); // [ 'aa', 'bb' ]
        console.log(target.match(/[ab]+/g)); // [ 'aa', 'bb' ]
        console.log(target.match(/[a-z]+/g)); // [ 'aa', 'bb', 'cc', 'dd' ]
        console.log(target.match(/[A-Za-z]+/g)); // [ 'aa', 'bb', 'cc', 'dd' ]
        console.log(target.match(/[0-9]+/g)); // [ '123', '456' ]
        ```

        - `\d`: 숫자
        - `\D`: 숫자가 아닌 문자
        - `\w`: 알파벳, 숫자, 언더스코어
        - `\W`: \w의 반대
        ```javascript
        target = 'aa bb cc dd 123 456 _@';
        console.log(target.match(/\d+/g)); // [ '123', '456' ]
        console.log(target.match(/\D+/g)); // [ 'aa bb cc dd ', ' ', ' _@' ]
        console.log(target.match(/\w+/g)); // [ 'aa', 'bb', 'cc', 'dd', '123', '456', '_' ]
        console.log(target.match(/\W+/g)); // [ ' ', ' ', ' ', ' ', ' ', ' ', '@' ]
        ```

        - `[…]` 내의 `^`: not
        ```javascript
        target = 'aa bb cc dd 123 456 _@';
        console.log(target.match(/[^0-9]+/g)); // [ 'aa bb cc dd ', ' ', ' _@' ]
        console.log(target.match(/[^a-z]+/g)); // [ ' ', ' ', ' ', ' 123 456 _@' ]
        ```

        - `[…]` 밖의 `^`: 시작 위치 검색
        - `$`: 마지막 위치 검색
        ```javascript
        target = 'https://www.google.com';
        console.log(/^https/.test(target)); // true
        console.log(/com$/.test(target)); // true
        ```

4. 예제
    - 특정 단어로 시작하는지 검사
    ```javascript
    const url = 'https://www.google.com';
    console.log(/^https?:\/\//.test(url)); // true
    ```

    - 특정 단어로 끝나는지 검사
    ```javascript
    const fileName = 'test.js';
    console.log(/js$/.test(fileName)); // true
    ```

    - 숫자로만 이루어진 문자열인지 검사
    ```javascript
    const target = '12345';
    console.log(/^\d+$/.test(target)); // true
    ```

    - 아이디로 사용 가능한지 검사
    ```javascript
    const id = 'hello123';
    console.log(/^[A-Za-z0-9]{6,12}$/.test(id)); // true
    ```

    - 핸드폰 번호 형식에 맞는지 검사
    ```javascript
    const phone = '010-1234-5678';
    console.log(/^\d{3}-\d{3,4}-\d{4}$/.test(phone)); // true
    ```

    - 특수 문자 포함 여부 검사
    ```javascript
    const target2 = 'hello#world';
    console.log(/[^A-Za-z0-9]/gi.test(target2)); // true
    ```

> ### 왜 사용해야 하는가?
1. **패턴 매칭**: 정규 표현식을 사용하면 문자열에서 특정 패턴을 쉽게 찾을 수 있음
2. **유효성 검사**: 입력된 데이터의 유효성을 검사할 수 있음
3. **문자열 조작**: 문자열을 검색하고, 치환하고, 분할하는 등의 작업을 효율적으로 수행할 수 있음

> ### 쉬운 요약
1. 정규 표현식은 "일정한 패턴을 가진 문자열의 집합을 표현하기 위해 사용하는 형식 언어"
    - 주로 문자열을 대상으로 한 패턴 매칭 기능을 제공

2. 주요 기능: 정규 표현식 생성, RegExp 메서드, 플래그와 패턴, 다양한 예제

> ### 비유
1. 탐정
    - 정규 표현식은 "문자열에서 특정 패턴을 찾는 탐정"과 같음
    - 예: 탐정이 단서를 찾아내는 것처럼, 정규 표현식을 사용하여 문자열에서 특정 패턴을 찾아냄

2. 필터
    - 정규 표현식은 "문자열을 걸러내는 필터"와 같음
    - 예: 필터를 사용하여 원하는 문자열만 걸러내는 것처럼, 정규 표현식을 사용하여 특정 패턴의 문자열을 걸러냄

[뒤로](javascript.md)
