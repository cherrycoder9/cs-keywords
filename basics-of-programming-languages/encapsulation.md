# 캡슐화

캡슐화(Encapsulation)는 객체지향 프로그래밍(OOP)의 핵심 원칙 중 하나로, 데이터와 그 데이터를 처리하는 메서드를 하나의 단위로 묶어 외부로부터 보호하는 개념임. 이를 통해 객체의 내부 상태를 은닉하고, 객체의 인터페이스를 통한 상호작용만을 허용함.

## 캡슐화의 주요 특징

- **정보 은닉**: 객체의 내부 구현을 숨기고, 필요한 부분만 외부에 노출함.
- **데이터 보호**: 객체의 상태를 보호하고, 무단 접근을 방지함.
- **유지보수성 향상**: 내부 구현 변경이 외부에 미치는 영향을 최소화함.

## 캡슐화 구현 예시 (Python)

```python
class BankAccount:
    def __init__(self, owner, initial_balance=0):
        self.__owner = owner
        self.__balance = initial_balance

    def deposit(self, amount):
        if amount > 0:
            self.__balance += amount
            return f"{amount}원이 입금되었습니다. 현재 잔액: {self.__balance}원"
        return "유효하지 않은 입금액입니다."

    def withdraw(self, amount):
        if 0 < amount <= self.__balance:
            self.__balance -= amount
            return f"{amount}원이 출금되었습니다. 현재 잔액: {self.__balance}원"
        return "잔액이 부족하거나 유효하지 않은 출금액입니다."

    def get_balance(self):
        return f"{self.__owner}님의 현재 잔액: {self.__balance}원"

# 객체 생성 및 사용
account = BankAccount("홍길동", 10000)
print(account.deposit(5000))   # 출력: 5000원이 입금되었습니다. 현재 잔액: 15000원
print(account.withdraw(3000))  # 출력: 3000원이 출금되었습니다. 현재 잔액: 12000원
print(account.get_balance())   # 출력: 홍길동님의 현재 잔액: 12000원

# print(account.__balance)  # AttributeError: 'BankAccount' object has no attribute '__balance'
```

## Java에서의 캡슐화 예시

```java
public class Employee {
    private String name;
    private double salary;

    public Employee(String name, double salary) {
        this.name = name;
        this.salary = salary;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        if (name != null && !name.isEmpty()) {
            this.name = name;
        }
    }

    public double getSalary() {
        return salary;
    }

    public void raiseSalary(double percentage) {
        if (percentage > 0) {
            this.salary += this.salary * (percentage / 100);
        }
    }

    public String getEmployeeInfo() {
        return "이름: " + name + ", 급여: " + salary + "원";
    }
}

public class Main {
    public static void main(String[] args) {
        Employee emp = new Employee("김철수", 3000000);
        System.out.println(emp.getEmployeeInfo());  // 출력: 이름: 김철수, 급여: 3000000.0원

        emp.raiseSalary(10);  // 10% 급여 인상
        System.out.println(emp.getEmployeeInfo());  // 출력: 이름: 김철수, 급여: 3300000.0원

        // emp.salary = 5000000;  // 컴파일 에러: salary는 private
    }
}
```

## 캡슐화의 장점

1. **데이터 무결성 유지**: 잘못된 데이터 접근과 수정을 방지함.
2. **코드 재사용성 증대**: 독립적으로 동작하는 캡슐화된 클래스는 다른 프로젝트에서도 쉽게 재사용할 수 있음.
3. **유지보수성 향상**: 내부 구현 변경이 외부 코드에 영향을 미치지 않아 유지보수가 용이함.
4. **모듈화 강화**: 시스템을 작은 단위로 나누어 관리할 수 있어 복잡한 시스템의 개발과 유지보수가 효율적임.

캡슐화는 객체의 속성과 행위를 하나로 묶어 객체의 자율성을 보장하고, 외부로부터의 잘못된 접근을 차단함. 이는 객체의 정보를 보호하고, 객체 간의 결합도를 낮추는 데 기여함. 결과적으로 소프트웨어의 품질을 향상시키고, 변경에 유연한 설계를 가능하게 함.

캡슐화를 통해 객체의 내부 구현을 숨기고 외부에는 필요한 인터페이스만을 제공함으로써, 객체의 사용과 내부 구현을 분리할 수 있음. 이는 '정보 은닉'이라는 객체지향 설계의 중요한 원칙을 실현하는 방법이며, 소프트웨어의 복잡성을 관리하는 데 큰 도움이 됨.
