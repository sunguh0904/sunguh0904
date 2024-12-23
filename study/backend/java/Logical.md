## Logical
> ### 논리 연산자란?
논리 연산자(Logical)는 컴퓨터에서 참(True)과 거짓(False)을 다루는 연산을 의미</br>
"이 조건이 맞나?", "두 조건이 모두 맞나?", "하나라도 맞나?"와 같은 질문을 처리할 때 사용

비유하자면, 논리 연산은 여러 스위치의 상태를 보고 전구를 켜거나 끄는 회로와 같음
- AND(그리고): 두 스위치가 모두 켜져야 전구가 켜짐
- OR(또는): 하나라도 켜져 있으면 전구가 켜짐
- NOT(부정): 스위치가 켜져 있으면 끄고, 꺼져 있으면 킴

> ### 논리 연산자의 예
- AND(그리고)
    - "우산도 챙겼고, 비도 오면 외출 가능" -> 두 조건이 모두 만족해야 함

- OR(또는)
    - "오늘 날씨가 맑거나, 비가 오더라도 실내에서 운동 가능" -> 하나라도 만족하면 됨

- NOT(부정)
    - "나는 배가 고프지 않다" -> 배고픈 상태(False)를 반대로 바꿔 표현

> ### 코드로 보기
1. AND 연산 (&&)
- 두 조건이 모두 참이어야 참을 반환
	```java
	boolean hasUmbrella = true;
	boolean isRaining = true;

	if (hasUmbrella && isRaining) {
		System.out.println("외출 가능합니다.");  // 출력: 외출 가능합니다.
	}
	```
- 두 조건이 모두 참이어야 참을 반환
	```java
	boolean hasUmbrella = true;
	boolean isRaining = true;

	if (hasUmbrella && isRaining) {
		System.out.println("외출 가능합니다.");  // 출력: 외출 가능합니다.
	}
	```

2. OR 연산 (||)
- 하나라도 참이면 참을 반환
	```java
	boolean isSunny = true;
	boolean isIndoorActivity = false;

	if (isSunny || isIndoorActivity) {
		System.out.println("외출 가능합니다.");  // 출력: 외출 가능합니다.
	}
	```

3. NOT 연산 (!)
- 조건의 참/거짓을 반대로 바꿈
	```java
	boolean isHungry = false;

	if (!isHungry) {
		System.out.println("배고프지 않습니다.");  // 출력: 배고프지 않습니다.
	}
	```

> ### 쉬운 요약
1.	논리 연산은 조건을 처리하는 연산
	- “이 조건이 맞나?”, “두 조건이 모두 맞나?”, “하나라도 맞나?“와 같은 질문을 처리

2.	연산자의 종류
	- AND(&&): 두 조건이 모두 참일 때만 참
	- OR(||): 하나라도 참이면 참
	- NOT(!): 조건의 참/거짓을 반대로 바꿈
3.	결과는 항상 참(true) 또는 거짓(false)
	- 논리 연산은 항상 “참” 또는 “거짓”이라는 명확한 답을 반환

> ### 비유
1.	AND는 “전구가 켜지려면 두 스위치 모두 켜야 함”
	- 두 조건이 모두 맞아야 결과가 참(True)
	- 예: “우산이 있고, 비가 오면 외출 가능”

2.	OR는 “하나라도 켜져 있으면 전구 켜짐”
	- 하나라도 맞으면 결과가 참(True)
	- 예: “날씨가 맑거나, 비가 와도 실내 활동 가능”
    
3.	NOT는 “스위치 상태를 반대로 바꾸기”
	- 참을 거짓으로, 거짓을 참으로 바꿈
	- 예: “배고프지 않다” → “배가 고프다”의 반대

[뒤로](java)