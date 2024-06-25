# 추상 클래스

추상 클래스(Abstract Class)는 객체지향 프로그래밍(OOP)에서 하나 이상의 추상 메서드를 포함하는 클래스임. 추상 메서드는 선언만 있고 구현이 없는 메서드로, 이를 상속받는 자식 클래스에서 반드시 구현해야 함. 추상 클래스는 직접 인스턴스화할 수 없으며, 상속을 통해서만 사용됨.

## 추상 클래스의 주요 특징

- **추상 메서드 포함**: 구현되지 않은 메서드를 포함하며, 자식 클래스에서 이를 반드시 구현해야 함.
- **부분적 구현 가능**: 일반 메서드와 추상 메서드를 모두 포함할 수 있어, 공통 기능을 제공할 수 있음.
- **인스턴스화 불가**: 추상 클래스 자체로는 객체를 생성할 수 없으며, 상속을 통해 사용됨.
- **계층 구조 정의**: 클래스 계층 구조에서 공통된 특성을 정의하는 데 사용됨.

## Python에서의 추상 클래스 예시

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

    def describe(self):
        return "이 도형은 2차원 평면 도형입니다."

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
print(rect.describe())
print(circle.describe())
```

## Java에서의 추상 클래스 예시

Java에서는 `abstract` 키워드를 사용하여 추상 클래스를 정의함.

```java
abstract class Employee {
    private String name;
    private int id;

    public Employee(String name, int id) {
        this.name = name;
        this.id = id;
    }

    public String getName() {
        return name;
    }

    public int getId() {
        return id;
    }

    public abstract double calculateSalary();

    public void displayInfo() {
        System.out.println("이름: " + name + ", ID: " + id);
    }
}

class FullTimeEmployee extends Employee {
    private double monthlySalary;

    public FullTimeEmployee(String name, int id, double monthlySalary) {
        super(name, id);
        this.monthlySalary = monthlySalary;
    }

    @Override
    public double calculateSalary() {
        return monthlySalary;
    }
}

class PartTimeEmployee extends Employee {
    private double hourlyRate;
    private int hoursWorked;

    public PartTimeEmployee(String name, int id, double hourlyRate, int hoursWorked) {
        super(name, id);
        this.hourlyRate = hourlyRate;
        this.hoursWorked = hoursWorked;
    }

    @Override
    public double calculateSalary() {
        return hourlyRate * hoursWorked;
    }
}

public class Main {
    public static void main(String[] args) {
        Employee fullTime = new FullTimeEmployee("홍길동", 1001, 3000000);
        Employee partTime = new PartTimeEmployee("김철수", 1002, 15000, 80);

        fullTime.displayInfo();
        System.out.println("급여: " + fullTime.calculateSalary() + "원");

        partTime.displayInfo();
        System.out.println("급여: " + partTime.calculateSalary() + "원");
    }
}
```

## 추상 클래스의 장점

1. **공통 기능 제공**: 여러 자식 클래스에서 공유할 수 있는 공통 기능을 구현함.
2. **일관성 보장**: 자식 클래스에서 반드시 구현해야 할 메서드를 정의하여 일관된 인터페이스를 제공함.
3. **코드 재사용성 증가**: 공통 기능을 한 곳에서 구현하여 여러 자식 클래스에서 재사용할 수 있음.
4. **유연한 설계**: 기본 구현을 제공하면서도 특정 기능의 구현을 자식 클래스에 위임할 수 있음.

## 추상 클래스와 인터페이스의 차이점

- **구현 정도**: 추상 클래스는 일부 메서드의 구현을 포함할 수 있지만, 인터페이스는 기본적으로 메서드 선언만 포함함.
- **다중 상속**: Java에서 클래스는 하나의 추상 클래스만 상속받을 수 있지만, 여러 인터페이스를 구현할 수 있음.
- **사용 목적**: 추상 클래스는 '관련된 클래스들의 공통 기능을 추출'하는 데 사용되며, 인터페이스는 '클래스의 행동을 정의'하는 데 사용됨.

추상 클래스는 객체지향 설계에서 중요한 역할을 함. 특히 템플릿 메서드 패턴(Template Method Pattern)과 같은 디자인 패턴을 구현할 때 유용하게 사용됨. 이를 통해 알고리즘의 구조를 정의하고 일부 단계를 하위 클래스에서 구현하도록 할 수 있음.

또한, 추상 클래스는 클래스 계층 구조에서 중간 레벨의 추상화를 제공하는 데 유용함. 이는 복잡한 시스템을 더 체계적으로 설계하고 관리하는 데 도움이 됨. 추상 클래스를 통해 공통 동작을 정의하고, 특정 동작의 구현을 자식 클래스에 위임함으로써, 코드의 재사용성과 확장성을 높일 수 있음.
