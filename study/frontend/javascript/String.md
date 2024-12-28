## JavaScript String Object
> ### String 객체란?
String 객체는 JavaScript에서 원시 타입인 문자열을 다룰 때 유용한 프로퍼티와 메서드를 제공하는 표준 빌트인 객체</br>
주로 문자열을 생성하고, 조작하고, 변환하는 데 사용됨

> ### String 객체의 주요 기능
1. String 생성자 함수
    ```javascript
    // new 연산자와 함께 호출하여 String 인스턴스를 생성
    const obj = new String();
    console.log(obj); // 인수 전달하지 않으면 빈 문자열을 할당한 객체 생성

    const obj2 = new String('홍길동');
    console.log(obj2); // 인수로 문자열 전달 시 전달 받은 문자열 할당

    // length 프로퍼티(문자열의 문자 개수)
    console.log(obj2.length);
    console.log(obj2[0]);

    // 문자열이 아닌 값을 인수로 전달했을 경우 문자열로 강제 변환
    const obj3 = new String(100);
    const obj4 = new String(null);
    console.log(obj3[0]);
    console.log(obj4[0]);
    ```

2. String 메서드
    - `String.prototype.indexOf`: 전달한 값과 일치하는 첫 번째 인덱스를 반환
    ```javascript
    const str = 'JavaScript';
    console.log(str.indexOf('a')); // 1
    console.log(str.indexOf('b')); // -1
    console.log(str.indexOf('a', 2)); // 3
    if (str.indexOf('a') !== -1) console.log('a가 있다');
    ```

    - `String.prototype.includes`: 하나의 문자열이 다른 문자열에 포함되어 있는지를 판별하고, 결과를 true 또는 false로 반환
    ```javascript
    const str = 'JavaScript';
    console.log(str.includes('a')); // true
    console.log(str.includes('b')); // false
    console.log(str.includes('a', 2)); // true
    if (str.includes('a')) console.log('a가 있다');
    ```

    - `String.prototype.search`: 인수로 전달 받은 정규 표현식과 매치하는 문자열을 검색하여 일치하는 문자열 인덱스를 반환
    ```javascript
    const str = 'JavaScript';
    console.log(str.search(/a/)); // 1
    console.log(str.search(/b/)); // -1
    ```

    - `String.prototype.startsWith`: 어떤 문자열이 특정 문자로 시작하는지 확인하여 결과를 true 혹은 false로 반환
    - `String.prototype.endsWith`: 어떤 문자열이 특정 문자로 끝나는지 확인하여 결과를 true 혹은 false로 반환
    ```javascript
    const str = 'JavaScript';
    console.log(str.startsWith('Ja')); // true
    console.log(str.startsWith('va', 2)); // true
    console.log(str.endsWith('pt')); // true
    console.log(str.endsWith('va', 4)); // true
    ```

    - `String.prototype.charAt`: 문자열에서 특정 인덱스에 위치하는 유니코드 단일 문자를 반환
    ```javascript
    const str = 'JavaScript';
    for (let i = 0; i < str.length; i++) console.log(str.charAt(i));
    ```

    - `String.prototype.substring`: string 객체의 시작 인덱스로부터 종료 인덱스 전까지 문자열의 부분 문자열을 반환
    ```javascript
    const str = 'JavaScript';
    console.log(str.substring(1, 4)); // "ava"
    console.log(str.substring(1)); // "avaScript"
    console.log(str.substring(4, 1)); // "ava"
    console.log(str.substring(-1)); // "JavaScript"
    console.log(str.substring(1, 20)); // "avaScript"
    ```

    - `String.prototype.slice`: 문자열의 일부를 추출하면서 새로운 문자열을 반환
    ```javascript
    const str = 'JavaScript';
    console.log(str.slice(1, 4)); // "ava"
    console.log(str.slice(1)); // "avaScript"
    console.log(str.slice(4, 1)); // ""
    console.log(str.slice(-1)); // "t"
    console.log(str.slice(1, 20)); // "avaScript"
    ```

    - `String.prototype.toUpperCase`: 문자열을 대문자로 변환해 반환
    - `String.prototype.toLowerCase`: 문자열을 소문자로 변환해 반환
    ```javascript
    const str = 'JavaScript';
    console.log(str.toUpperCase()); // "JAVASCRIPT"
    console.log(str.toLowerCase()); // "javascript"
    ```

    - `String.prototype.trim`: 문자열 앞뒤 공백 문자 제거 후 반환
    ```javascript
    const str2 = ' JavaScript ';
    console.log(str2.trim()); // "JavaScript"
    ```

    - `String.prototype.repeat`: 전달받은 정수만큼 반복해 연결한 새로운 문자열을 반환
    ```javascript
    const str = 'JavaScript';
    console.log(str.repeat()); // ""
    console.log(str.repeat(0)); // ""
    console.log(str.repeat(1)); // "JavaScript"
    console.log(str.repeat(2)); // "JavaScriptJavaScript"
    console.log(str.repeat(2.5)); // "JavaScriptJavaScript"
    // console.log(str.repeat(-1)); // RangeError: Invalid count value
    ```

    - `String.prototype.replace`: 첫 번째 인수로 전달 받은 문자열 또는 정규표현식을 검색하여 두 번째 인수로 전달한 문자열로 치환한 문자열 반환
    ```javascript
    const str = 'JavaScript';
    console.log(str.replace('Java', 'Type')); // TypeScript
    console.log(str.replace('a', 'b')); // JbvaScript
    console.log(str.replace(/j/i, 'Z')); // ZavaScript
    ```

    - `String.prototype.split`: 첫 번째 인수로 전달한 문자열 또는 정규식을 검색하여 문자열을 구분한 후 분리된 각 문자열로 이루어진 배열 반환
    ```javascript
    const str3 = 'Hello, Everyone! Nice to see you again.';
    console.log(str3.split(' ')); // 공백을 구분하여 배열로 반환
    console.log(str3.split('')); // 인수로 빈 문자열을 전달하면 각 문자를 모두 분리
    console.log(str3.split()); // 인수를 생략하면 문자열 전체를 단일 요소로 하는 배열 반환
    console.log(str3.split(' ', 5)); // 두 번째 인수로 배열의 길이 지정
    ```

> ### 왜 사용해야 하는가?
1. **문자열 처리**: String 객체를 사용하면 문자열과 관련된 다양한 작업을 쉽게 수행할 수 있음
2. **문자열 변환**: 문자열을 대문자, 소문자 등으로 변환하여 다양한 형식으로 데이터를 처리할 수 있음
3. **문자열 조작**: 문자열을 검색하고, 치환하고, 분할하는 등의 작업을 효율적으로 수행할 수 있음

> ### 쉬운 요약
1. String 객체는 "원시 타입인 문자열을 다룰 때 유용한 프로퍼티와 메서드를 제공하는 표준 빌트인 객체"
    - 주로 문자열을 생성하고, 조작하고, 변환하는 데 사용됨

2. 주요 기능: String 생성자 함수, String 메서드

> ### 비유
1. 편집기
    - String 객체는 "문자열을 편집하는 편집기"와 같음
    - 예: 편집기를 사용하여 문자열을 검색하고, 치환하고, 분할하는 것처럼, String 객체를 사용하여 문자열을 조작

2. 변환기
    - String 객체는 "문자열을 다양한 형식으로 변환하는 변환기"와 같음
    - 예: 변환기를 사용하여 문자열을 대문자, 소문자 등으로 변환하는 것처럼, String 객체를 사용하여 문자열을 변환

[뒤로](javascript.md)
