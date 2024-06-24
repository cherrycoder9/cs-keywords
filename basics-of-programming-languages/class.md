# 클래스

클래스는 객체지향 프로그래밍(OOP)에서 객체를 정의하는 템플릿임. 객체의 속성과 메서드를 포함하는 설계도 역할을 수행하며, 코드 재사용성과 프로그램 구조의 명확성을 향상시킴.

## 클래스의 구성 요소

- **속성**: 클래스 내에서 정의된 데이터. 객체의 상태를 표현함.
- **메서드**: 클래스에 정의된 함수. 객체가 수행할 수 있는 동작을 나타냄.
- **생성자**: 객체 생성 시 호출되는 특별한 메서드. 객체의 초기 상태를 설정함.

## 클래스 정의와 객체 생성

```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age
    
    def greet(self):
        return f"안녕하세요, 저는 {self.name}이고 {self.age}살입니다."

# 객체 생성 및 사용
person1 = Person("홍길동", 30)
print(person1.name)       # 출력: 홍길동
print(person1.greet())    # 출력: 안녕하세요, 저는 홍길동이고 30살입니다.
```

## 클래스의 특징

- **상속**: 기존 클래스의 속성과 메서드를 새로운 클래스가 물려받음. 코드 재사용성 증대.
- **다형성**: 같은 이름의 메서드가 다른 클래스에서 다르게 구현될 수 있음. 유연성과 확장성 향상.
- **캡슐화**: 클래스 내부 요소를 외부로부터 숨기고, 공개 메서드를 통해서만 접근 가능하게 함. 데이터 무결성 보호.

## 상속 예시

```python
class Animal:
    def __init__(self, name):
        self.name = name
    
    def speak(self):
        raise NotImplementedError("하위 클래스에서 이 메서드를 구현해야 합니다.")

class Dog(Animal):
    def speak(self):
        return f"{self.name}(이)가 멍멍!"

class Cat(Animal):
    def speak(self):
        return f"{self.name}(이)가 야옹!"

dog = Dog("바둑이")
cat = Cat("나비")
print(dog.speak())  # 출력: 바둑이(이)가 멍멍!
print(cat.speak())  # 출력: 나비(이)가 야옹!
```

## 캡슐화 예시

```python
class BankAccount:
    def __init__(self, owner, balance=0):
        self.owner = owner
        self.__balance = balance  # 비공개 속성

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

account = BankAccount("김철수")
account.deposit(10000)
print(account.get_balance())  # 출력: 10000
account.withdraw(3000)
print(account.get_balance())  # 출력: 7000
```

클래스는 OOP의 기본 구성 요소로, 복잡한 소프트웨어 시스템을 모듈화하고 구조화하는 데 중요한 역할을 함. 클래스를 통해 현실 세계의 개념을 프로그래밍적으로 모델링할 수 있으며, 이는 직관적이고 유지보수가 용이한 코드 작성을 가능하게 함. 상속, 다형성, 캡슐화 등의 특성을 활용하여 유연하고 확장 가능한 소프트웨어 구조를 설계할 수 있음.
