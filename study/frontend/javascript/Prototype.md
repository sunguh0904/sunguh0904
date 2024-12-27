## JavaScript Prototype
> ### 프로토타입이란?
프로토타입(Prototype)은 JavaScript에서 객체 지향 프로그래밍을 지원하기 위해 사용되는 개념</br>
모든 객체는 프로토타입을 가지고 있으며, 이 프로토타입을 통해 다른 객체의 속성과 메서드를 상속받을 수 있음

> ### 프로토타입의 주요 특징
1. 프로토타입 체인: 객체가 다른 객체의 속성과 메서드를 상속받는 구조
    ```javascript
    function Person(name, age) {
        this.name = name;
        this.age = age;
    }

    Person.prototype.greet = function() {
        console.log('Hello, my name is ' + this.name);
    };

    const john = new Person('John', 30);
    john.greet(); // Hello, my name is John
    ```

2. 프로토타입 상속: 객체가 다른 객체의 프로토타입을 상속받아 속성과 메서드를 공유
    ```javascript
    function Employee(name, age, job) {
        Person.call(this, name, age);
        this.job = job;
    }

    Employee.prototype = Object.create(Person.prototype);
    Employee.prototype.constructor = Employee;

    const jane = new Employee('Jane', 25, 'Developer');
    jane.greet(); // Hello, my name is Jane
    console.log(jane.job); // Developer
    ```

3. 프로토타입 메서드: 프로토타입에 메서드를 정의하여 모든 인스턴스에서 공유
    ```javascript
    Person.prototype.sayAge = function() {
        console.log('I am ' + this.age + ' years old');
    };

    john.sayAge(); // I am 30 years old
    jane.sayAge(); // I am 25 years old
    ```

4. 프로토타입 속성: 프로토타입에 속성을 정의하여 모든 인스턴스에서 공유
    ```javascript
    Person.prototype.species = 'Homo sapiens';

    console.log(john.species); // Homo sapiens
    console.log(jane.species); // Homo sapiens
    ```

> ### 왜 사용해야 하는가?
1. **코드 재사용**: 프로토타입을 사용하면 속성과 메서드를 공유하여 코드 재사용성을 높일 수 있음
2. **메모리 효율성**: 프로토타입에 정의된 메서드와 속성은 모든 인스턴스에서 공유되므로 메모리 사용을 줄일 수 있음
3. **객체 지향 프로그래밍**: 프로토타입을 사용하여 객체 지향 프로그래밍의 상속 개념을 구현할 수 있음

> ### 쉬운 요약
1. 프로토타입은 "JavaScript에서 객체 지향 프로그래밍을 지원하기 위해 사용되는 개념"
    - 모든 객체는 프로토타입을 가지고 있으며, 이를 통해 다른 객체의 속성과 메서드를 상속받을 수 있음

2. 주요 특징: 프로토타입 체인, 프로토타입 상속, 프로토타입 메서드, 프로토타입 속성

> ### 비유
1. 유전자
    - 프로토타입은 "부모로부터 자식에게 전달되는 유전자"와 같음
    - 예: 부모의 유전자를 통해 자식이 부모의 특성을 상속받는 것처럼, 객체가 프로토타입을 통해 다른 객체의 속성과 메서드를 상속

2. 청사진
    - 프로토타입은 "건물을 짓기 위한 청사진"과 같음
    - 예: 청사진을 통해 여러 건물이 동일한 구조를 가지는 것처럼, 프로토타입을 통해 여러 객체가 동일한 속성과 메서드를 공유

[뒤로](javascript.md)
