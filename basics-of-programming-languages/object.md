# 객체

객체는 객체지향 프로그래밍(OOP)의 핵심 개념으로, 데이터와 그 데이터를 조작하는 메서드를 하나로 묶은 자기 완결적 단위임. 클래스를 통해 정의되며, 클래스는 객체의 청사진 역할을 수행함.

## 객체의 구성 요소

- **속성**: 객체의 상태를 나타내는 데이터. 필드 또는 멤버 변수라고도 불림.
- **메서드**: 객체의 행동을 정의하는 함수. 객체가 수행할 수 있는 작업을 표현함.

## 객체의 특징

- **캡슐화**: 데이터와 메서드를 하나의 단위로 묶어 외부 접근을 제한함. 데이터 보호와 무결성 유지에 기여함.
- **상속**: 기존 클래스의 특성을 새로운 클래스가 물려받음. 코드 재사용성을 높이고 계층적 관계를 구현함.
- **다형성**: 동일한 인터페이스로 다양한 객체를 다룰 수 있게 함. 유연한 코드 설계를 가능하게 함.

## 객체의 생성과 사용

객체는 클래스의 인스턴스화를 통해 생성됨. 생성 시 클래스의 생성자가 호출되어 객체의 초기 상태를 설정함.

```java
// Java 예시
public class Car {
    private String make;
    private String model;
    private int year;

    public Car(String make, String model, int year) {
        this.make = make;
        this.model = model;
        this.year = year;
    }

    public String startEngine() {
        return String.format("The %d %s %s's engine is now running.", year, make, model);
    }
}

// 객체 생성 및 사용
Car myCar = new Car("Tesla", "Model 3", 2023);
System.out.println(myCar.startEngine());
// 출력: The 2023 Tesla Model 3's engine is now running.
```

## 캡슐화 구현

캡슐화는 객체의 내부 상태를 외부로부터 보호하고, 제어된 방식으로만 접근할 수 있게 함.

```python
# Python 예시
class BankAccount:
    def __init__(self, owner, balance=0):
        self.__owner = owner
        self.__balance = balance

    def deposit(self, amount):
        if amount > 0:
            self.__balance += amount
            return True
        return False

    def withdraw(self, amount):
        if 0 < amount <= self.__balance:
            self.__balance -= amount
            return True
        return False

    def get_balance(self):
        return self.__balance

# 사용 예
account = BankAccount("Alice")
account.deposit(1000)
print(account.get_balance())  # 출력: 1000
account.withdraw(500)
print(account.get_balance())  # 출력: 500
```

## 상속과 다형성

상속을 통해 기존 클래스의 특성을 새로운 클래스에 물려줄 수 있음. 다형성은 같은 인터페이스를 통해 다양한 객체를 다룰 수 있게 함.

```python
class Animal:
    def speak(self):
        pass

class Dog(Animal):
    def speak(self):
        return "Woof!"

class Cat(Animal):
    def speak(self):
        return "Meow!"

def animal_sound(animal):
    print(animal.speak())

# 다형성 활용
dog = Dog()
cat = Cat()
animal_sound(dog)  # 출력: Woof!
animal_sound(cat)  # 출력: Meow!
```

객체는 현실 세계의 개념이나 사물을 프로그래밍적으로 모델링하는 데 효과적임. 복잡한 시스템을 객체들의 상호작용으로 표현함으로써, 직관적이고 모듈화된 코드 구조를 만들 수 있음. 이를 통해 대규모 소프트웨어 시스템의 개발과 유지보수가 용이해짐.
