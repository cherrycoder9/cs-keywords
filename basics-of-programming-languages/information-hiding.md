# 정보 은닉

정보 은닉(Information Hiding)은 객체지향 프로그래밍(OOP)의 핵심 원칙 중 하나로, 객체의 내부 상태와 구현 세부사항을 외부로부터 숨기는 개념임. 이를 통해 객체의 데이터 무결성을 보호하고, 객체 간의 결합도를 낮춰 유지보수성과 확장성을 향상시킴.

## 정보 은닉의 주요 목적

- **데이터 무결성 보호**: 객체의 내부 상태를 외부의 직접적인 접근으로부터 보호함.
- **구현의 독립성 유지**: 객체의 내부 구현 변경이 외부 코드에 영향을 미치지 않도록 함.
- **코드 유지보수성 향상**: 객체의 내부 구현을 자유롭게 변경할 수 있어 유지보수가 용이해짐.

## 정보 은닉 구현 방법

정보 은닉은 주로 접근 제어자(Access Modifiers)를 사용하여 구현함.

- **Private**: 같은 클래스 내에서만 접근 가능
- **Protected**: 같은 패키지 내의 클래스와 상속 관계의 클래스에서 접근 가능
- **Public**: 모든 곳에서 접근 가능

## 정보 은닉 예시 (Python)

```python
class Employee:
    def __init__(self, name, salary):
        self.__name = name
        self.__salary = salary

    def get_name(self):
        return self.__name

    def get_salary(self):
        return self.__salary

    def raise_salary(self, percentage):
        if 0 < percentage <= 20:
            self.__salary += self.__salary * (percentage / 100)
            return True
        return False

    def __str__(self):
        return f"직원 이름: {self.__name}, 급여: {self.__salary}원"

# 객체 생성 및 사용
emp = Employee("홍길동", 3000000)
print(emp)  # 출력: 직원 이름: 홍길동, 급여: 3000000원

emp.raise_salary(10)
print(emp)  # 출력: 직원 이름: 홍길동, 급여: 3300000.0원

# print(emp.__salary)  # AttributeError: 'Employee' object has no attribute '__salary'
```

## Java에서의 정보 은닉 예시

```java
public class BankAccount {
    private String accountNumber;
    private double balance;

    public BankAccount(String accountNumber, double initialBalance) {
        this.accountNumber = accountNumber;
        this.balance = initialBalance;
    }

    public void deposit(double amount) {
        if (amount > 0) {
            balance += amount;
            System.out.println(amount + "원이 입금되었습니다.");
        } else {
            System.out.println("유효하지 않은 입금액입니다.");
        }
    }

    public void withdraw(double amount) {
        if (amount > 0 && amount <= balance) {
            balance -= amount;
            System.out.println(amount + "원이 출금되었습니다.");
        } else {
            System.out.println("유효하지 않은 출금액이거나 잔액이 부족합니다.");
        }
    }

    public double getBalance() {
        return balance;
    }

    public String getAccountInfo() {
        return "계좌번호: " + accountNumber + ", 잔액: " + balance + "원";
    }
}

public class Main {
    public static void main(String[] args) {
        BankAccount account = new BankAccount("1234-5678", 10000);
        
        account.deposit(5000);
        System.out.println(account.getAccountInfo());
        
        account.withdraw(3000);
        System.out.println(account.getAccountInfo());
        
        // account.balance = 1000000;  // 컴파일 에러: balance는 private
    }
}
```

## 정보 은닉의 장점

1. **데이터 무결성 유지**: 객체의 상태를 외부의 부적절한 접근으로부터 보호함.
2. **캡슐화 강화**: 객체의 데이터와 관련 동작을 하나의 단위로 묶어 관리함.
3. **유지보수성 향상**: 객체의 내부 구현 변경이 외부 코드에 영향을 미치지 않아 유지보수가 용이함.
4. **모듈화 촉진**: 시스템을 독립적인 모듈로 나누어 관리할 수 있어 복잡한 시스템의 개발과 유지보수가 효율적임.

정보 은닉은 객체의 내부 구현을 숨기고 필요한 인터페이스만을 외부에 노출함으로써 객체 간의 결합도를 낮추고 응집도를 높임. 이는 소프트웨어의 유연성과 재사용성을 증가시키며, 변경에 대한 영향을 최소화함.

또한, 정보 은닉은 객체의 책임을 명확히 정의하고 객체 간의 상호작용을 제어함으로써 시스템의 복잡성을 관리하는 데 도움을 줌. 이는 대규모 소프트웨어 시스템의 설계와 개발에 있어 핵심적인 역할을 함.
