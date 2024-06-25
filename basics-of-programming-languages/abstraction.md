# 추상화

추상화(Abstraction)는 객체지향 프로그래밍(OOP)의 핵심 원칙 중 하나로, 복잡한 시스템의 본질적인 특징을 추출하여 간단하고 일반화된 모델을 만드는 과정임. 불필요한 세부사항은 숨기고 중요한 개념이나 기능에 집중하여 시스템의 복잡성을 관리함.

## 추상화의 주요 특징

- **복잡성 감소**: 핵심 정보만 노출하고 불필요한 세부사항을 숨김.
- **유지보수성 향상**: 공통 인터페이스를 통해 다양한 구현을 일관되게 관리함.
- **코드 재사용성 증가**: 추상화된 개념을 다양한 상황에서 재사용할 수 있음.

## 추상화 구현 방법

추상화는 주로 추상 클래스(Abstract Class)와 인터페이스(Interface)를 통해 구현됨.

### 추상 클래스 예시 (Python)

Python에서는 `abc` 모듈을 사용하여 추상 클래스를 정의함.

```python
from abc import ABC, abstractmethod

class Shape(ABC):
    @abstractmethod
    def area(self):
        pass

    @abstractmethod
    def perimeter(self):
        pass

class Rectangle(Shape):
    def __init__(self, width, height):
        self.width = width
        self.height = height

    def area(self):
        return self.width * self.height

    def perimeter(self):
        return 2 * (self.width + self.height)

class Circle(Shape):
    def __init__(self, radius):
        self.radius = radius

    def area(self):
        return 3.14 * self.radius ** 2

    def perimeter(self):
        return 2 * 3.14 * self.radius

# 객체 생성 및 사용
rect = Rectangle(5, 3)
circle = Circle(4)

print(f"직사각형 면적: {rect.area()}, 둘레: {rect.perimeter()}")
print(f"원 면적: {circle.area():.2f}, 둘레: {circle.perimeter():.2f}")
```

### 인터페이스 예시 (Java)

Java에서는 `interface` 키워드를 사용하여 인터페이스를 정의함.

```java
interface Vehicle {
    void start();
    void stop();
    void accelerate(int speed);
}

class Car implements Vehicle {
    @Override
    public void start() {
        System.out.println("자동차 시동을 겁니다.");
    }

    @Override
    public void stop() {
        System.out.println("자동차를 정지합니다.");
    }

    @Override
    public void accelerate(int speed) {
        System.out.println("자동차가 " + speed + "km/h로 가속합니다.");
    }
}

class Bicycle implements Vehicle {
    @Override
    public void start() {
        System.out.println("자전거 주행을 시작합니다.");
    }

    @Override
    public void stop() {
        System.out.println("자전거를 정지합니다.");
    }

    @Override
    public void accelerate(int speed) {
        System.out.println("자전거가 " + speed + "km/h로 페달링합니다.");
    }
}

public class Main {
    public static void main(String[] args) {
        Vehicle car = new Car();
        Vehicle bicycle = new Bicycle();

        car.start();
        car.accelerate(60);
        car.stop();

        bicycle.start();
        bicycle.accelerate(20);
        bicycle.stop();
    }
}
```

## 추상화의 장점

1. **복잡성 관리**: 시스템의 본질적인 특성에 집중하여 복잡성을 줄임.
2. **유지보수성 향상**: 공통 인터페이스를 통해 다양한 구현을 일관되게 관리할 수 있어 유지보수가 용이함.
3. **코드 재사용성 증가**: 추상화된 개념을 다양한 상황에서 재사용할 수 있음.
4. **유연성 향상**: 인터페이스나 추상 클래스를 통해 구현을 쉽게 변경할 수 있어 시스템의 유연성이 증가함.
5. **설계의 단순화**: 복잡한 시스템을 더 간단하고 이해하기 쉬운 모델로 표현할 수 있음.

추상화는 객체지향 설계의 기반이 되는 원칙으로, 복잡한 시스템을 더 관리하기 쉽고 이해하기 쉬운 형태로 모델링하는 데 핵심적인 역할을 함. 이를 통해 개발자는 시스템의 핵심 기능에 집중할 수 있으며, 코드의 재사용성과 확장성을 높일 수 있음.

추상화는 또한 '인터페이스와 구현의 분리' 원칙을 실현하는 데 중요한 역할을 함. 이는 시스템의 다양한 부분들이 서로 독립적으로 발전할 수 있게 하며, 변경에 대한 영향을 최소화함. 이러한 특성은 대규모 소프트웨어 시스템의 개발과 유지보수에 있어 매우 중요함.
