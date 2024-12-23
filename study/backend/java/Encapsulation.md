## Encapsulation
> ### 캡슐화란?
캡슐화(Encapsulation)는 데이터와 메소드를 하나로 묶고, 외부에서 직접 접근하지 못하도록 보호하는 객체 지향 프로그래밍의 중요한 개념</br>
데이터를 직접 수정하거나 잘못된 방식으로 접근하지 못하도록 접근 제한자(Access Modifier)를 사용하여 제어

> ### 캡슐화의 예
- 자동차 운전
    - 운전자는 핸들, 브레이크 페달을 통해 자동차를 제어하지만, 엔진 내부 작동 방식을 직접 수정하지는 않음

- 은행 계좌
    - 계좌 잔액은 캡슐화되어 있어, ATM이나 앱을 통해 입출금만 가능
    - 잔액 데이터를 직접 수정할 수 없음

- TV 리모컨
    - 리모컨 버튼으로 채널을 바꾸지만, TV 내부 작동 방식을 알 필요는 없음

> ### 코드로 보기
1. 캡슐화 전 (문제점)
- 데이터를 아무나 변경할 수 있어 문제가 발생할 수 있음
```java
class Account {
    public int balance;  // 누구나 접근 가능한 변수

    public void deposit(int amount) {
        balance += amount;
    }
}

public class Main {
    public static void main(String[] args) {
        Account account = new Account();
        account.balance = -100;  // 외부에서 잔액을 마음대로 변경
        System.out.println(account.balance);  // 출력: -100
    }
}
```

2. 캡슐화 후 (해결책)
- `private`으로 데이터를 보호하고, `getter`와 `setter` 메소드를 통해 안전하게 접근
```java
class Account {
    private int balance;  // 외부에서 직접 접근 불가

    // 잔액 확인
    public int getBalance() {
        return balance;
    }

    // 입금
    public void deposit(int amount) {
        if (amount > 0) {
            balance += amount;
        } else {
            System.out.println("잘못된 금액입니다.");
        }
    }

    // 출금
    public void withdraw(int amount) {
        if (amount > 0 && balance >= amount) {
            balance -= amount;
        } else {
            System.out.println("출금할 수 없습니다.");
        }
    }
}

public class Main {
    public static void main(String[] args) {
        Account account = new Account();
        account.deposit(1000);  // 안전하게 입금
        account.withdraw(500); // 안전하게 출금
        System.out.println(account.getBalance());  // 출력: 500
    }
}
```

> ### 쉬운 요약
1. 캡슐화는 데이터와 메소드를 하나로 묶고, 외부 접근 제하나여 보호하는 것
    - 중요한 데이터(필드)를 `private`로 보호하고, 필요한 경우에만 `public` 메소드로 접근을 허용

2. 장점
    - 데이터 보호: 잘못된 접근이나 수정으로부터 데이터를 보호
    - 유지보수 용이: 데이터를 안전하게 다룰 수 있어 프로그램의 안정성을 높임
    - 코드 재사용성: 클래스 내부 구현을 변경해도 외부 코드 영향을 주지 않음

3. 핵심 요소
    - 접근 제한자: `private`, `public`, `protected`를 사용해 접근을 제어
    - Getter/Setter 메소드: 데이터를 안전하게 읽고 수정할 수 있도록 제공

> ### 비유
1. 자동차 운전
    - 운전자는 핸들과 페달을 사용하지만, 엔진 내부를 건드리지 못함
    - 엔진은 캡슐화되어 있고, 제어 장치(핸들, 페달)가 제공

2. 은행 계좌
    - 계좌 잔액은 보호되고, 입출금 버튼(메소드)을 통해서만 안전하게 잔액을 변경할 수 있음

3. 약 캡슐
    - 약 성분은 캡슐 안에 보호되어 있고, 필요한 성분만 안전하게 작동

[뒤로](java.md)