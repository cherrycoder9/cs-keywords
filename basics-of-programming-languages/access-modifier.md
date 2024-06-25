# 접근 제어자

접근 제어자(Access Modifiers)는 객체지향 프로그래밍(OOP)에서 클래스, 메서드, 속성 등의 접근 범위를 제어하는 키워드임. 이를 통해 데이터 캡슐화를 강화하고, 객체의 내부 구현을 외부로부터 보호할 수 있음.

## 접근 제어자의 종류

- **Public**: 모든 곳에서 접근 가능. 제한 없이 사용 가능함.
- **Protected**: 같은 패키지 내의 클래스와 상속 관계의 클래스에서 접근 가능함.
- **Private**: 같은 클래스 내에서만 접근 가능. 외부에서 직접 접근 불가능함.
- **Default** (Package-private): 같은 패키지 내에서만 접근 가능 (Java에서 사용).

## Python에서의 접근 제어

Python은 언어 차원에서 접근 제어자를 직접 지원하지 않지만, 명명 규칙을 통해 유사한 기능을 구현할 수 있음.

```python
class Person:
    def __init__(self, name, age, ssn):
        self.name = name      # public
        self._age = age       # protected (관례상)
        self.__ssn = ssn      # private (이름 맹글링 적용)

    def get_ssn(self):
        return self.__ssn

person = Person("홍길동", 30, "123-45-6789")
print(person.name)     # 출력: 홍길동
print(person._age)     # 출력: 30 (경고: 직접 접근은 권장되지 않음)
# print(person.__ssn)  # AttributeError 발생
print(person.get_ssn())  # 출력: 123-45-6789
```

## Java에서의 접근 제어자

Java는 명시적인 접근 제어자를 제공함.

```java
public class BankAccount {
    public String accountHolder;
    protected double balance;
    private String accountNumber;

    public BankAccount(String accountHolder, double initialBalance, String accountNumber) {
        this.accountHolder = accountHolder;
        this.balance = initialBalance;
        this.accountNumber = accountNumber;
    }

    public void deposit(double amount) {
        if (amount > 0) {
            balance += amount;
            System.out.println(amount + "원이 입금되었습니다.");
        }
    }

    protected void updateBalance(double newBalance) {
        this.balance = newBalance;
    }

    private String getAccountNumber() {
        return accountNumber;
    }

    public String getAccountInfo() {
        return "계좌 소유자: " + accountHolder + ", 잔액: " + balance + "원";
    }
}

public class Main {
    public static void main(String[] args) {
        BankAccount account = new BankAccount("김철수", 10000, "1234-5678");
        
        System.out.println(account.accountHolder);  // 출력: 김철수
        account.deposit(5000);  // 출력: 5000원이 입금되었습니다.
        System.out.println(account.getAccountInfo());  // 출력: 계좌 소유자: 김철수, 잔액: 15000.0원
        
        // account.balance = 1000000;  // 컴파일 에러 (다른 패키지에서 접근 시)
        // System.out.println(account.accountNumber);  // 컴파일 에러
    }
}
```

## 접근 제어자의 역할

- **캡슐화 강화**: 객체의 내부 상태를 외부로부터 보호함.
- **정보 은닉**: 클래스의 내부 구현을 숨기고, 필요한 인터페이스만 공개함.
- **코드 유지보수성 향상**: 외부에 노출되지 않은 코드는 클래스 내부에서만 관리되어, 변경 시 영향 범위를 최소화함.
- **보안성 강화**: 중요한 데이터나 동작을 외부로부터 숨겨 보안을 강화함.

접근 제어자는 OOP의 핵심 원칙 중 하나인 캡슐화를 실현하는 중요한 도구임. 적절한 접근 제어자 사용은 코드의 안정성, 유지보수성, 확장성을 크게 향상시킴. 특히 대규모 프로젝트나 팀 단위 개발에서 접근 제어자의 중요성이 더욱 부각됨.

객체의 속성과 메서드에 대한 접근을 제한함으로써, 객체의 무결성을 보장하고 예기치 않은 상태 변경을 방지할 수 있음. 또한, 클래스의 내부 구현을 숨김으로써 향후 구현 변경 시 외부 코드에 미치는 영향을 최소화할 수 있음. 이는 소프트웨어의 유연성과 견고성을 높이는 데 기여함.
