## JavaScript Object Literals
> ### 객체 리터럴이란?
객체 리터럴(Object Literal)은 중괄호 `{}`를 사용하여 객체를 생성하는 간단한 방법</br>
주로 속성과 값을 한 번에 정의하여 객체를 생성하는 데 사용됨

> ### 객체 리터럴의 주요 특징
1. 속성 정의: 객체의 속성과 값을 정의
    ```javascript
    // 객체 리터럴을 사용하여 객체 생성
    const person = {
        name: 'John',
        age: 30,
        job: 'Developer'
    };
    console.log(person.name); // John
    console.log(person.age); // 30
    console.log(person.job); // Developer
    ```

2. 메서드 정의: 객체의 메서드를 정의
    ```javascript
    // 객체 리터럴을 사용하여 메서드 정의
    const person = {
        name: 'John',
        age: 30,
        job: 'Developer',
        greet: function() {
            console.log('Hello, my name is ' + this.name);
        }
    };
    person.greet(); // Hello, my name is John
    ```

3. 동적 속성: 대괄호 표기법을 사용하여 동적으로 속성에 접근
    ```javascript
    // 대괄호 표기법을 사용하여 동적으로 속성에 접근
    const propertyName = 'age';
    console.log(person[propertyName]); // 30
    ```

4. 단축 속성명: 변수 이름과 속성 이름이 동일할 때 단축 속성명을 사용
    ```javascript
    const name = 'John';
    const age = 30;
    const job = 'Developer';

    // 단축 속성명을 사용하여 객체 생성
    const person = { name, age, job };
    console.log(person.name); // John
    console.log(person.age); // 30
    console.log(person.job); // Developer
    ```

> ### 왜 사용해야 하는가?
1. **간단한 객체 생성**: 객체 리터럴을 사용하면 간단하게 객체를 생성할 수 있음
2. **가독성 향상**: 객체의 속성과 값을 한 번에 정의하여 코드의 가독성을 향상시킬 수 있음
3. **동적 속성 접근**: 대괄호 표기법을 사용하여 동적으로 속성에 접근할 수 있음

> ### 쉬운 요약
1. 객체 리터럴은 "중괄호 `{}`를 사용하여 객체를 생성하는 간단한 방법"
    - 주로 속성과 값을 한 번에 정의하여 객체를 생성하는 데 사용됨

2. 주요 특징: 속성 정의, 메서드 정의, 동적 속성 접근, 단축 속성명

> ### 비유
1. 레고 블록
    - 객체 리터럴은 "레고 블록을 사용하여 구조물을 만드는 것"과 같음
    - 예: 레고 블록을 조립하여 하나의 구조물을 만드는 것처럼, 속성과 값을 조합하여 객체를 생성

2. 명함
    - 객체 리터럴은 "명함에 정보를 기입하는 것"과 같음
    - 예: 명함에 이름, 나이, 직업을 기입하는 것처럼, 객체에 속성과 값을 정의

[뒤로](javascript.md)
