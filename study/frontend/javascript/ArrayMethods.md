## JavaScript Array Methods
> ### 배열 메소드란?
배열 메소드는 JavaScript에서 배열을 조작하고 데이터를 처리하는 데 사용되는 다양한 메소드</br>
주로 배열의 요소를 추가, 제거, 검색, 결합, 분할, 정렬하는 데 사용됨

> ### 주요 배열 메소드
1. `Array.prototype.indexOf`, `Array.prototype.lastIndexOf`, `Array.prototype.includes`
    - `indexOf`: 배열에서 요소가 위치한 인덱스를 반환
    - `lastIndexOf`: 배열의 요소가 위치한 마지막 인덱스를 반환
    - `includes`: 배열에 해당 요소가 포함되어 있는지 여부를 반환
    ```javascript
    const foodList = ['물회', '삼계탕', '냉면', '수박', '물회'];
    console.log(foodList.indexOf('물회')); // 0
    console.log(foodList.indexOf('물회', 1)); // 4
    console.log(foodList.indexOf('삼겹살')); // -1
    console.log(foodList.lastIndexOf('물회')); // 4
    console.log(foodList.lastIndexOf('물회', 1)); // 0
    console.log(foodList.lastIndexOf('삼겹살')); // -1
    console.log(foodList.includes('물회')); // true
    console.log(foodList.includes('삼겹살')); // false
    ```

2. `Array.prototype.push`, `Array.prototype.pop`
    - `push`: 배열의 맨 뒤에 요소를 추가
    - `pop`: 배열의 맨 뒤에 요소를 제거
    ```javascript
    const chineseFood = ['짜장면', '짬뽕', '우동'];
    chineseFood.push('탕수육');
    chineseFood.push('양장피');
    console.log(chineseFood); // ['짜장면', '짬뽕', '우동', '탕수육', '양장피']
    console.log(chineseFood.pop()); // 양장피
    console.log(chineseFood.pop()); // 탕수육
    console.log(chineseFood.pop()); // 우동
    console.log(chineseFood); // ['짜장면', '짬뽕']
    ```

3. `Array.prototype.unshift`, `Array.prototype.shift`
    - `unshift`: 배열의 맨 앞에 요소를 추가
    - `shift`: 배열의 맨 앞 요소를 제거 후 반환
    ```javascript
    const chickenList = ['양념치킨', '후라이드', '파닭'];
    chickenList.unshift('간장치킨');
    chickenList.unshift('마늘치킨');
    console.log(chickenList); // ['마늘치킨', '간장치킨', '양념치킨', '후라이드', '파닭']
    console.log(chickenList.shift()); // 마늘치킨
    console.log(chickenList.shift()); // 간장치킨
    console.log(chickenList.shift()); // 양념치킨
    console.log(chickenList); // ['후라이드', '파닭']
    ```

4. `Array.prototype.concat`
    - `concat`: 두 개 이상의 배열을 결합
    ```javascript
    const idol1 = ['아이브', '오마이걸'];
    const idol2 = ['트와이스', '에스파'];
    const idol3 = ['블랙핑크', '레드벨벳'];
    const mix = idol1.concat(idol2);
    const mix2 = idol3.concat(idol1, idol2);
    console.log(mix); // ['아이브', '오마이걸', '트와이스', '에스파']
    console.log(mix2); // ['블랙핑크', '레드벨벳', '아이브', '오마이걸', '트와이스', '에스파']
    ```

5. `Array.prototype.slice`, `Array.prototype.splice`
    - `slice`: 배열의 요소를 선택하여 잘라내기
    - `splice`: 배열의 인덱스 위치의 요소를 제거 및 추가
    ```javascript
    const front = ['HTML', 'CSS', 'JavaScript', 'jQuery'];
    console.log(front.slice(1, 3)); // ['CSS', 'JavaScript']
    console.log(front); // ['HTML', 'CSS', 'JavaScript', 'jQuery']
    console.log(front.splice(3, 1, 'React')); // ['jQuery']
    console.log(front); // ['HTML', 'CSS', 'JavaScript', 'React']
    ```

6. `Array.prototype.join`
    - `join`: 배열을 구분자로 결합하여 문자열로 반환
    ```javascript
    const snackList = ['사탕', '초콜렛', '껌', '과자'];
    console.log(snackList.join()); // '사탕,초콜렛,껌,과자'
    console.log(snackList.join('/')); // '사탕/초콜렛/껌/과자'
    ```

7. `Array.prototype.reverse`
    - `reverse`: 배열의 순서를 뒤집음
    ```javascript
    console.log([1, 2, 3, 4, 5].reverse()); // [5, 4, 3, 2, 1]
    ```

> ### 왜 사용해야 하는가?
1. **데이터 조작**: 배열 메소드를 사용하면 배열의 데이터를 쉽게 조작할 수 있음
2. **코드 간결화**: 배열 메소드를 사용하여 코드를 간결하게 작성할 수 있음
3. **다양한 기능 제공**: 배열 메소드는 다양한 기능을 제공하여 데이터를 효율적으로 처리할 수 있음

> ### 쉬운 요약
1. 배열 메소드는 "배열을 조작하고 데이터를 처리하는 데 사용되는 다양한 메소드"
    - 주로 배열의 요소를 추가, 제거, 검색, 결합, 분할, 정렬하는 데 사용됨

2. 주요 메소드: `indexOf`, `lastIndexOf`, `includes`, `push`, `pop`, `unshift`, `shift`, `concat`, `slice`, `splice`, `join`, `reverse`

> ### 비유
1. 도구 상자
    - 배열 메소드는 "다양한 도구가 들어있는 도구 상자"와 같음
    - 예: 도구 상자에서 필요한 도구를 꺼내어 작업을 수행하는 것처럼, 배열 메소드를 사용하여 배열을 조작

2. 요리 도구
    - 배열 메소드는 "요리를 위한 다양한 도구"와 같음
    - 예: 요리를 할 때 다양한 도구를 사용하여 재료를 준비하고 요리를 완성하는 것처럼, 배열 메소드를 사용하여 데이터를 처리

[뒤로](javascript.md)
