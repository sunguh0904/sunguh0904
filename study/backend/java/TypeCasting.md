## TypeCasting
> ### 형변환 이란?
형변환(TyepCasting)은 데이터 형태를 다른 형태로 바꾸는 것을 말함</br>
비유하자면, 큰 컵에 있는 물을 작은 컵에 담거나, 작은 컵의 물을 큰 컵에 옮기는 과정과 비슷

- 작은 컵 -> 큰 겁: 물이 넘치지 않으므로 안전하게 옮길 수 있음
- 큰 컵 -> 작은 컵: 물이 넘칠 수 있기 때문에 조심해야 함

> ### 형변환의 예
- 큰 용기에 작은 것을 넣기
    - 큰 컵에 담긴 물은 작은 컵으로 쉽게 옮길 수 있지만, 넘치는 경우 주의해야 함

- 다른 단위로 변환하기
    - 1,000원을 "천원"이라고 표현하거나, 1km를 "1,000km"로 표현하는 것처럼 데이터를 다른 방식으로 해석

> ### 코드로 보기
1. 작은 데이터 -> 큰 데이터 (자동 변환)
- 작은 데이터를 큰 데이터로 바꿀 때는 문제가 없음
    ```java
    int num = 100;
    double largeNum = num;  // int → double, 자동으로 변환
    System.out.println(largeNum); // 출력: 100.0
    ```

2. 큰 데이터 -> 작은 데이터 (명시적 변환)
- 큰 데이터를 작은 데이터로 바꿀 때는 손실 가능성이 있으므로 명시적으로 처리해야 함
    ```java
    double pi = 3.14159;
    int roundedPi = (int) pi;  // double → int, 명시적 변환
    System.out.println(roundedPi); // 출력: 3
    ```

3. 문자열 -> 숫자 (파싱)
- 문자열 데이터를 숫자로 변환할 때는 별도의 메소드를 사용해야 됨
    ```java
    String ageString = "20";
    int age = Integer.parseInt(ageString);  // String → int
    System.out.println(age); // 출력: 20
    ```

> ### 쉬운 요약
1. 형변환은 데이터의 모양을 바꾸는 작업
    - 큰 컵에서 작은 컵으로 물을 옮기거나, 숫자를 문자열로 바꾸는 것과 비슷

2. 두 가지 유형
    - 자동 변환: 작은 데이터 -> 큰 데이터 (안전)
    - 명시적 변환: 큰 데이터 -> 작은 데이터 (손실 가능성 있음)

3. 문자열 데이터도 숫자로 변환 가능
    - "20"이라는 문자열을 숫자 20으로 바꿀 수 있음

> ### 비유
1. 큰 컵 -> 작은 컵
    - 큰 컵의 물을 작은 컵에 담으면 넘칠 수 있으므로 주의해야 함

2. 다른 단위로 바꾸기
    - 1km를 1,000mFH VYGUSGKRJSK, 1,000원을 천 원으로 바꾸는 과정과 비슷

3. 번역기 사용하기
    - 영어 문장을 한국어로 바꾸는 것처럼, 데이터를 적합한 형태로 변환

[뒤로](java.md)