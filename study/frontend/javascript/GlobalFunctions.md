## JavaScript Built-in Global Functions
> ### 빌트인 전역 함수란?
빌트인 전역 함수는 JavaScript에서 어디서든 호출할 수 있는 전역 객체의 함수</br>
주로 데이터 타입 검사, 문자열 변환, URI 인코딩/디코딩 등을 수행하는 함수가 포함됨

> ### 주요 빌트인 전역 함수
1. `isFinite`
    - 전달 받은 인수가 정상적인 유한수인지 검사하여 유한수이면 true를 반환하고, 무한수이면 false를 반환
    - 전달 받은 인수가 숫자가 아닌 경우 숫자로 타입 변환 후 검사를 수행하며, NaN으로 평가되는 값이면 false를 반환
    ```javascript
    console.log(isFinite(10)); // true
    console.log(isFinite('10')); // true
    console.log(isFinite(null)); // true
    console.log(isFinite(Infinity)); // false
    console.log(isFinite(-Infinity)); // false
    console.log(isFinite(NaN)); // false
    console.log(isFinite('abc')); // false
    ```

2. `isNaN`
    - 전달 받은 인수가 NaN인지 검사하여 그 검사 결과를 불리언 타입으로 반환
    - 전달 받은 인수가 숫자가 아닌 경우 숫자로 타입 변환 후 검사를 수행
    ```javascript
    console.log(isNaN(NaN)); // true
    console.log(isNaN(10)); // false
    console.log(isNaN('abc')); // true
    console.log(isNaN('10')); // false
    console.log(isNaN('')); // false ('' => 0)
    console.log(isNaN(true)); // false (true => 1)
    console.log(isNaN(false)); // false (false => 0)
    console.log(isNaN(undefined)); // true
    console.log(isNaN({})); // true
    ```

3. `parseFloat`
    - 전달받은 문자열 인수를 부동 소수점 숫자, 실수로 해석하여 반환
    ```javascript
    console.log(parseFloat('10.01')); // 10.01
    console.log(parseFloat('10')); // 10
    console.log(parseFloat('10 20 30')); // 10
    console.log(parseFloat('10cm')); // 10
    console.log(parseFloat('GS25')); // NaN
    console.log(parseFloat(' 1004 ')); // 1004
    ```

4. `parseInt`
    - 전달받은 문자열 인수를 정수로 해석하여 반환
    ```javascript
    console.log(parseInt('10')); // 10
    console.log(parseInt('10.01')); // 10
    ```

5. `encodeURI`
    - URI(인터넷에 있는 자원을 나타내는 유일한 주소)를 문자열로 전달받아 이스케이프 처리를 위해 인코딩
    - 네트워크를 통해 정보를 공유할 때 어떤 시스템에서도 읽을 수 있는 아스키 문자 셋으로 변환
    ```javascript
    const uri = 'http://greedy.com?name=홍길동&job=student';
    const enc = encodeURI(uri);
    console.log(enc); // http://greedy.com?name=%ED%99%8D%EA%B8%B8%EB%8F%99&job=student
    ```

6. `decodeURI`
    - 인코딩 된 URI를 인수로 전달 받아 이스케이프 처리 이전으로 디코딩
    ```javascript
    const enc = 'http://greedy.com?name=%ED%99%8D%EA%B8%B8%EB%8F%99&job=student';
    const dec = decodeURI(enc);
    console.log(dec); // http://greedy.com?name=홍길동&job=student
    ```

7. `encodeURIComponent`
    - URI 구성 요소를 인수로 전달 받아 알파벳, 0~9의 숫자, - _ . ! ~ * ’ ( ) 문자는 제외하고 인코딩
    - 쿼리 스트링 구분자로 사용 되는 =, ?, &까지 인코딩
    ```javascript
    const uriComp = 'name=홍길동&job=student';
    const encComp = encodeURIComponent(uriComp);
    console.log(encComp); // name%3D%ED%99%8D%EA%B8%B8%EB%8F%99%26job%3Dstudent
    ```

8. `decodeURIComponent`
    - 인코딩 된 URI를 인수로 전달 받아 이스케이프 처리 이전으로 디코딩
    ```javascript
    const encComp = 'name%3D%ED%99%8D%EA%B8%B8%EB%8F%99%26job%3Dstudent';
    const decComp = decodeURIComponent(encComp);
    console.log(decComp); // name=홍길동&job=student
    ```

> ### 왜 사용해야 하는가?
1. **데이터 타입 검사**: 빌트인 전역 함수를 사용하면 데이터 타입을 쉽게 검사할 수 있음
2. **문자열 변환**: 문자열을 숫자나 URI로 변환하여 다양한 작업을 수행할 수 있음
3. **URI 인코딩/디코딩**: URI를 인코딩하거나 디코딩하여 네트워크 통신을 원활하게 할 수 있음

> ### 쉬운 요약
1. 빌트인 전역 함수는 "어디서든 호출할 수 있는 전역 객체의 함수"
    - 주로 데이터 타입 검사, 문자열 변환, URI 인코딩/디코딩 등을 수행

2. 주요 함수: `isFinite`, `isNaN`, `parseFloat`, `parseInt`, `encodeURI`, `decodeURI`, `encodeURIComponent`, `decodeURIComponent`

> ### 비유
1. 다목적 도구
    - 빌트인 전역 함수는 "다양한 작업을 수행할 수 있는 다목적 도구"와 같음
    - 예: 다목적 도구를 사용하여 여러 작업을 수행하는 것처럼, 전역 함수를 사용하여 다양한 작업을 수행

2. 번역기
    - 빌트인 전역 함수는 "데이터를 변환하는 번역기"와 같음
    - 예: 번역기를 사용하여 언어를 변환하는 것처럼, 전역 함수를 사용하여 데이터를 변환

[뒤로](javascript.md)
