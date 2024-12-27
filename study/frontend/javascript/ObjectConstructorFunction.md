## JavaScript Object Constructor Function
> ### 객체 생성자 함수란?
객체 생성자 함수(Object Constructor Function)는 새로운 객체를 생성하고 초기화하는 데 사용되는 함수</br>
주로 동일한 구조를 가진 여러 객체를 생성할 때 사용됨

> ### 객체 생성자 함수 정의 방법
1. 생성자 함수 정의: `function` 키워드를 사용하여 생성자 함수 정의
    ```javascript
    // 생성자 함수를 사용하여 객체 정의
    function Person(name, age, job) {
        this.name = name;
        this.age = age;
        this.job = job;
    }

    // 새로운 객체 생성
    const person1 = new Person('John', 30, 'Developer');
    const person2 = new Person('Jane', 25, 'Designer');

    console.log(person1.name); // John
    console.log(person2.name); // Jane
    ```

2. 프로토타입 메서드 정의: 생성자 함수의 프로토타입에 메서드 추가
    ```javascript
    // 생성자 함수 정의
    function Person(name, age, job) {
        this.name = name;
        this.age = age;
        this.job = job;
    }

    // 프로토타입에 메서드 추가
    Person.prototype.greet = function() {
        console.log('Hello, my name is ' + this.name);
    };

    // 새로운 객체 생성
    const person1 = new Person('John', 30, 'Developer');
    person1.greet(); // Hello, my name is John
    ```

> ### 왜 사용해야 하는가?
1. **코드 재사용**: 생성자 함수를 사용하면 동일한 구조를 가진 객체를 쉽게 생성할 수 있음
2. **유지보수 용이**: 생성자 함수를 사용하여 객체 생성 로직을 중앙 집중화할 수 있음
3. **프로토타입 활용**: 생성자 함수의 프로토타입을 사용하여 메서드를 공유할 수 있음

> ### 쉬운 요약
1. 객체 생성자 함수는 "새로운 객체를 생성하고 초기화하는 함수"
    - 주로 동일한 구조를 가진 여러 객체를 생성할 때 사용됨

2. 주요 특징: 생성자 함수 정의, 프로토타입 메서드 정의

> ### 비유
1. 청사진
    - 객체 생성자 함수는 "건물을 짓기 위한 청사진"과 같음
    - 예: 청사진을 사용하여 동일한 구조를 가진 여러 건물을 짓는 것처럼, 생성자 함수를 사용하여 동일한 구조를 가진 여러 객체를 생성

2. 공장
    - 객체 생성자 함수는 "제품을 생산하는 공장"과 같음
    - 예: 공장에서 동일한 제품을 대량 생산하는 것처럼, 생성자 함수를 사용하여 동일한 구조를 가진 여러 객체를 생성

[뒤로](javascript.md)
