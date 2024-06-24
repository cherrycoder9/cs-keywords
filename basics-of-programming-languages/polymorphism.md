# 다형성

다형성(Polymorphism)은 객체지향 프로그래밍(OOP)의 핵심 개념 중 하나로, 동일한 인터페이스를 통해 다양한 객체를 다룰 수 있게 하는 특성임. 이를 통해 코드의 유연성과 확장성을 크게 향상시킬 수 있음.

## 다형성의 종류

- **컴파일 시간 다형성**: 함수 오버로딩과 연산자 오버로딩을 통해 구현됨.
- **런타임 다형성**: 메서드 오버라이딩을 통해 구현되며, 객체의 실제 타입에 따라 다른 메서드가 호출됨.

## 메서드 오버라이딩 예시

```python
class Animal:
    def speak(self):
        return "동물 소리"

class Dog(Animal):
    def speak(self):
        return "멍멍!"

class Cat(Animal):
    def speak(self):
        return "야옹!"

animals = [Dog(), Cat(), Animal()]

for animal in animals:
    print(animal.speak())  

# 출력:
# 멍멍!
# 야옹!
# 동물 소리
```

## 다중 디스패치 구현

Python에서는 직접적인 함수 오버로딩을 지원하지 않지만, 다중 디스패치를 통해 유사한 기능을 구현할 수 있음.

```python
from functools import singledispatch

@singledispatch
def add(a):
    return a

@add.register(int)
def _(a, b):
    return a + b

@add.register(str)
def _(a, b):
    return f"{a} {b}"

print(add(1))         # 출력: 1
print(add(1, 2))      # 출력: 3
print(add("Hello", "world"))  # 출력: Hello world
```

## 인터페이스를 통한 다형성

추상 클래스나 인터페이스를 사용하여 다형성을 구현할 수 있음. 이를 통해 다양한 객체를 동일한 방식으로 다룰 수 있음.

```python
from abc import ABC, abstractmethod
import math

class Shape(ABC):
    @abstractmethod
    def area(self):
        pass

class Rectangle(Shape):
    def __init__(self, width, height):
        self.width = width
        self.height = height

    def area(self):
        return self.width * self.height

class Circle(Shape):
    def __init__(self, radius):
        self.radius = radius

    def area(self):
        return math.pi * (self.radius ** 2)

shapes = [Rectangle(3, 4), Circle(5)]

for shape in shapes:
    print(f"면적: {shape.area():.2f}")

# 출력:
# 면적: 12.00
# 면적: 78.54
```

다형성은 OOP의 강력한 특성으로, 코드의 재사용성과 유지보수성을 크게 향상시킴. 동일한 인터페이스를 통해 다양한 객체를 다룰 수 있게 함으로써, 시스템의 확장성과 유연성을 증대시킴. 이는 특히 대규모 소프트웨어 시스템에서 중요한 역할을 함.

다형성을 효과적으로 활용하면 코드의 의존성을 줄이고, 새로운 기능을 추가할 때 기존 코드의 수정을 최소화할 수 있음. 이는 "개방-폐쇄 원칙(Open-Closed Principle)"을 실현하는 데 도움이 되며, 소프트웨어의 유지보수와 확장을 용이하게 함.
