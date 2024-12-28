## JavaScript Date Object
> ### Date 객체란?
Date 객체는 JavaScript에서 날짜와 시간을 위한 메서드를 제공하는 표준 빌트인 객체이면서 생성자 함수</br>
주로 날짜와 시간을 생성하고, 조작하고, 형식화하는 데 사용됨

> ### Date 객체의 주요 기능
1. Date 생성자 함수
    ```javascript
    // 1. new Date() : 현재 날짜와 시간을 가지는 Date 객체 반환
    console.log(new Date());

    // 2. new Date(milliseconds) : 1970년 1월 1일 00:00:00(UTC)를 기점으로 인수로 전달된 밀리초만큼 경과한 날짜와 시간을 나타내는 Date 객체 반환
    console.log(new Date(0)); // 1970-01-01T00:00:00.000Z
    console.log(new Date(24 * 60 * 60 * 1000)); // 1970-01-02T00:00:00.000Z

    // 3. new Date(dateString) : 날짜와 시간을 나타내는 문자열을 인수로 전달하면 지정된 날짜와 시간을 나타내는 Date 객체 반환
    console.log(new Date('Jul 26, 2022 09:00:00')); // 2022-07-26T00:00:00.000Z
    console.log(new Date('2022/07/26/09:00:00')); // 2022-07-26T00:00:00.000Z

    // 4. new Date(year, month[, day, hour, minute, second, millisecond]) : 연, 월, 일, 시, 분, 초, 밀리초를 의미하는 숫자를 인수로 전달하면 지정된 날짜와 시간을 나타내는 Date 객체 반환
    console.log(new Date(2022, 1)); // 2022-01-31T15:00:00.000Z
    console.log(new Date(2022, 1, 1, 9, 0, 0, 0)); // 2022-02-01T00:00:00.000Z
    ```

2. Date 메서드
    - `Date.now`: 1970년 1월 1일 00:00:00(UTC)을 기점으로 현재 시간까지 경과한 밀리초를 숫자로 반환
    - `Date.parse`: 1970년 1월 1일 00:00:00(UTC)을 기점으로 인수로 전달된 지정 시간까지의 밀리초를 숫자로 반환
    - `Date.UTC`: 1970년 1월 1일 00:00:00(UTC)을 기점으로 인수로 전달된 지정 시간까지의 밀리초를 숫자로 반환
    ```javascript
    console.log(Date.now()); // 현재 시간까지 경과한 밀리초 반환
    console.log(Date.parse('Jan 1, 1970 09:00:00')); // 0
    console.log(Date.parse('Jan 1, 1970 09:00:00 UTC')); // 32400000
    console.log(Date.UTC(1970, 0, 1)); // 0
    ```

    - 연, 월, 일, 요일, 시, 분, 초 반환
    ```javascript
    const date = new Date();
    console.log(date.getFullYear()); // 년
    console.log(date.getMonth()); // 월
    console.log(date.getDate()); // 일
    console.log(date.getDay()); // 요일 (일요일부터 월요일을 0~6으로 반환)
    console.log(date.getHours()); // 시
    console.log(date.getMinutes()); // 분
    console.log(date.getSeconds()); // 초
    console.log(date.getMilliseconds()); // 밀리세컨
    ```

    - 연, 월, 일, 시, 분, 초 설정
    ```javascript
    const date = new Date();
    date.setFullYear(2020);
    date.setMonth(0);
    date.setDate(1);
    date.setHours(9);
    date.setMinutes(10);
    date.setSeconds(10);
    date.setMilliseconds(10);
    console.log(date); // 2020-01-01T00:10:10.010Z
    ```

    - `Date.getTime`: 1970년 1월 1일 00:00:00(UTC)을 기점으로 경과된 밀리초를 반환
    - `Date.setTime`: 1970년 1월 1일 00:00:00(UTC)을 기점으로 경과된 밀리초를 설정
    ```javascript
    const date = new Date();
    console.log(date.getTime());
    date.setTime(5 * 24 * 60 * 60 * 1000);
    console.log(date); // 1970-01-06T00:00:00.000Z
    ```

    - `Date.prototype.getTimezoneOffset`: UTC와 Date 객체에 지정된 로케일 시간과의 차이를 분 단위로 반환
    ```javascript
    const today = new Date();
    console.log(today.getTimezoneOffset()); // -540
    console.log(today.getTimezoneOffset() / 60); // -9
    ```

    - `Date.prototype.to___String`: 사람이 읽을 수 있는 형식의 문자열로 Date 객체의 날짜 반환
    ```javascript
    console.log(today.toString());
    console.log(today.toDateString());
    console.log(today.toTimeString());
    console.log(today.toISOString());
    console.log(today.toLocaleString());
    console.log(today.toLocaleTimeString());
    ```

> ### 왜 사용해야 하는가?
1. **날짜와 시간 처리**: Date 객체를 사용하면 날짜와 시간을 쉽게 생성하고 조작할 수 있음
2. **정확한 시간 계산**: Date 객체의 메서드를 사용하여 정확한 시간 계산을 수행할 수 있음
3. **형식화된 출력**: Date 객체를 사용하여 날짜와 시간을 다양한 형식으로 출력할 수 있음

> ### 쉬운 요약
1. Date 객체는 "날짜와 시간을 위한 메서드를 제공하는 표준 빌트인 객체이면서 생성자 함수"
    - 주로 날짜와 시간을 생성하고, 조작하고, 형식화하는 데 사용됨

2. 주요 기능: Date 생성자 함수, Date 메서드

> ### 비유
1. 시계
    - Date 객체는 "시간을 측정하고 표시하는 시계"와 같음
    - 예: 시계를 사용하여 현재 시간을 확인하고, 시간을 설정하는 것처럼, Date 객체를 사용하여 날짜와 시간을 생성하고 조작

2. 달력
    - Date 객체는 "날짜를 기록하고 관리하는 달력"과 같음
    - 예: 달력을 사용하여 날짜를 확인하고, 일정을 기록하는 것처럼, Date 객체를 사용하여 날짜와 시간을 관리

[뒤로](javascript.md)
