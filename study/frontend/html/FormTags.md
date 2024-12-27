## HTML 폼 태그
> ### 폼 관련 태그란?
폼 관련 태그는 HTML에서 사용자 입력을 받을 수 있는 폼을 생성하고 관리하는 데 사용되는 태그</br>
주로 입력 필드, 버튼, 레이블 등을 정의하여 사용자와 상호작용할 수 있는 폼을 구성하는 데 사용됨

> ### 주요 폼 관련 태그
1. `<form>`: 폼을 정의하는 태그
    ```html
    <!-- 폼을 정의 -->
    <form action="/submit" method="post">
        <label for="name">Name:</label>
        <input type="text" id="name" name="name">
        <input type="submit" value="Submit">
    </form>
    ```

2. `<input>`: 사용자 입력을 받을 수 있는 필드를 정의하는 태그
    ```html
    <!-- 텍스트 입력 필드를 정의 -->
    <input type="text" id="name" name="name">
    <!-- 비밀번호 입력 필드를 정의 -->
    <input type="password" id="password" name="password">
    <!-- 제출 버튼을 정의 -->
    <input type="submit" value="Submit">
    ```

3. `<label>`: 입력 필드에 대한 레이블을 정의하는 태그
    ```html
    <!-- 입력 필드에 대한 레이블을 정의 -->
    <label for="name">Name:</label>
    <input type="text" id="name" name="name">
    ```

4. `<textarea>`: 여러 줄의 텍스트를 입력받을 수 있는 필드를 정의하는 태그
    ```html
    <!-- 여러 줄의 텍스트를 입력받을 수 있는 필드를 정의 -->
    <textarea id="message" name="message" rows="4" cols="50"></textarea>
    ```

5. `<select>`: 드롭다운 목록을 정의하는 태그
    ```html
    <!-- 드롭다운 목록을 정의 -->
    <label for="options">Choose an option:</label>
    <select id="options" name="options">
        <option value="option1">Option 1</option>
        <option value="option2">Option 2</option>
        <option value="option3">Option 3</option>
    </select>
    ```

6. `<button>`: 버튼을 정의하는 태그
    ```html
    <!-- 버튼을 정의 -->
    <button type="submit">Submit</button>
    ```

> ### 왜 사용해야 하는가?
1. **사용자 입력 수집**: 폼 관련 태그를 사용하면 사용자로부터 입력을 받을 수 있음
2. **데이터 전송**: 폼을 통해 사용자 입력 데이터를 서버로 전송할 수 있음
3. **웹 표준 준수**: HTML 태그를 사용하여 웹 표준을 준수할 수 있음

> ### 쉬운 요약
1. 폼 관련 태그는 "HTML에서 사용자 입력을 받을 수 있는 폼을 생성하고 관리하는 데 사용되는 태그"
    - 주로 입력 필드, 버튼, 레이블 등을 정의하여 사용자와 상호작용할 수 있는 폼을 구성하는 데 사용됨

2. 사용자 입력 수집, 데이터 전송, 웹 표준 준수 등을 제공

> ### 비유
1. 설문지
    - 폼 관련 태그는 설문지와 같음
    - 예: 사용자로부터 다양한 정보를 수집

2. 은행 양식
    - 폼 관련 태그는 은행 양식과 같음
    - 예: 사용자로부터 필요한 정보를 입력받아 처리

[뒤로](html.md)
