## JavaScript Properties
> ### 속성이란?
속성(Property)은 객체의 상태나 특성을 나타내는 값</br>
주로 객체의 데이터를 저장하고, 그 데이터를 참조하거나 변경하는 데 사용됨

> ### 속성 정의 방법
1. 점 표기법: 객체의 속성에 접근하고 값을 설정
    ```javascript
    // 객체 생성
    const person = {
        name: 'John',
        age: 30
    };

    // 점 표기법을 사용하여 속성에 접근
    console.log(person.name); // John
    console.log(person.age); // 30

    // 점 표기법을 사용하여 속성 값 설정
    person.name = 'Doe';
    console.log(person.name); // Doe
    ```

2. 대괄호 표기법: 동적으로 속성에 접근하고 값을 설정
    ```javascript
    // 객체 생성
    const person = {
        name: 'John',
        age: 30
    };

    // 대괄호 표기법을 사용하여 속성에 접근
    console.log(person['name']); // John
    console.log(person['age']); // 30

    // 대괄호 표기법을 사용하여 속성 값 설정
    person['name'] = 'Doe';
    console.log(person['name']); // Doe
    ```

> ### 속성의 주요 특징
1. **동적 속성 추가**: 객체에 동적으로 속성을 추가할 수 있음
    ```javascript
    // 객체에 동적으로 속성 추가
    person.job = 'Developer';
    console.log(person.job); // Developer
    ```

2. **속성 삭제**: 객체의 속성을 삭제할 수 있음
    ```javascript
    // 객체의 속성 삭제
    delete person.age;
    console.log(person.age); // undefined
    ```

3. **속성 존재 여부 확인**: 객체에 특정 속성이 존재하는지 확인할 수 있음
    ```javascript
    // 객체에 특정 속성이 존재하는지 확인
    console.log('name' in person); // true
    console.log('age' in person); // false
    ```

> ### 왜 사용해야 하는가?
1. **데이터 저장**: 속성을 사용하면 객체의 데이터를 저장하고 참조할 수 있음
2. **동적 데이터 관리**: 동적으로 속성을 추가하거나 삭제하여 데이터를 관리할 수 있음
3. **유연성**: 점 표기법과 대괄호 표기법을 사용하여 유연하게 속성에 접근할 수 있음

> ### 쉬운 요약
1. 속성은 "객체의 상태나 특성을 나타내는 값"
    - 주로 객체의 데이터를 저장하고, 그 데이터를 참조하거나 변경하는 데 사용됨

2. 주요 특징: 동적 속성 추가, 속성 삭제, 속성 존재 여부 확인

> ### 비유
1. 사전
    - 속성은 "사전의 단어와 뜻"과 같음
    - 예: 사전에서 단어를 찾아 뜻을 확인하는 것처럼, 객체에서 속성을 찾아 값을 확인

2. 명함
    - 속성은 "명함에 기입된 정보"와 같음
    - 예: 명함에 이름, 나이, 직업을 기입하는 것처럼, 객체에 속성과 값을 정의

[뒤로](javascript.md)
