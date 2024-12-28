## JavaScript Strict Mode
> ### Strict Mode란?
Strict Mode는 JavaScript에서 더 엄격한 문법과 실행을 적용하여 오류를 줄이고, 안전한 코드를 작성할 수 있도록 도와주는 모드</br>
주로 코드의 잠재적인 문제를 사전에 발견하고, 예기치 않은 동작을 방지하기 위해 사용됨

> ### Strict Mode 사용 방법
1. 전역에서 Strict Mode 사용
    ```javascript
    'use strict';

    // Strict Mode가 적용된 코드
    function myFunction() {
        // ...
    }
    ```

2. 함수 내에서 Strict Mode 사용
    ```javascript
    function myFunction() {
        'use strict';
        // Strict Mode가 적용된 코드
        // ...
    }
    ```

> ### Strict Mode의 주요 특징
1. 암시적 전역 변수 사용 금지
    ```javascript
    'use strict';
    x = 10; // ReferenceError: x is not defined
    ```

2. 삭제할 수 없는 속성 삭제 금지
    ```javascript
    'use strict';
    var obj = {};
    Object.defineProperty(obj, 'x', { value: 10, configurable: false });
    delete obj.x; // TypeError: Cannot delete property 'x' of #<Object>
    ```

3. 중복된 매개변수 이름 금지
    ```javascript
    'use strict';
    function myFunction(x, x) {
        // SyntaxError: Duplicate parameter name not allowed in this context
    }
    ```

4. with 문 사용 금지
    ```javascript
    'use strict';
    with (Math) {
        // SyntaxError: Strict mode code may not include a with statement
        x = cos(2);
    }
    ```

5. this의 값이 undefined로 설정
    ```javascript
    'use strict';
    function myFunction() {
        console.log(this); // undefined
    }
    myFunction();
    ```

> ### 왜 사용해야 하는가?
1. **오류 발견**: Strict Mode를 사용하면 코드의 잠재적인 오류를 사전에 발견할 수 있음
2. **안전한 코드 작성**: Strict Mode를 사용하면 더 안전하고 예측 가능한 코드를 작성할 수 있음
3. **최적화 가능성 향상**: Strict Mode를 사용하면 JavaScript 엔진이 코드를 더 잘 최적화할 수 있음

> ### 쉬운 요약
1. Strict Mode는 "더 엄격한 문법과 실행을 적용하여 오류를 줄이고, 안전한 코드를 작성할 수 있도록 도와주는 모드"
    - 주로 코드의 잠재적인 문제를 사전에 발견하고, 예기치 않은 동작을 방지하기 위해 사용됨

2. 주요 특징: 암시적 전역 변수 사용 금지, 삭제할 수 없는 속성 삭제 금지, 중복된 매개변수 이름 금지, with 문 사용 금지, this의 값이 undefined로 설정

> ### 비유
1. 안전 규칙
    - Strict Mode는 "안전 규칙을 적용하여 사고를 방지하는 것"과 같음
    - 예: 안전 규칙을 적용하여 작업장에서 사고를 방지하는 것처럼, Strict Mode를 사용하여 코드의 오류를 방지

2. 엄격한 검사
    - Strict Mode는 "엄격한 검사를 통해 품질을 보장하는 것"과 같음
    - 예: 제품의 품질을 보장하기 위해 엄격한 검사를 하는 것처럼, Strict Mode를 사용하여 코드의 품질을 보장

[뒤로](javascript.md)
