# 오버라이딩

오버라이딩(Overriding)은 객체지향 프로그래밍(OOP)에서 자식 클래스가 부모 클래스의 메서드를 재정의하는 기능임. 이를 통해 자식 클래스는 상속받은 메서드의 동작을 자신의 필요에 맞게 변경하거나 확장할 수 있음.

## 오버라이딩의 목적

- 특정 동작의 재정의: 자식 클래스의 특성에 맞는 메서드 구현
- 다형성 구현: 동일한 메서드 호출로 객체별 다른 동작 수행
- 코드 재사용성 증대: 부모 클래스 메서드를 기반으로 필요한 부분만 수정

## 오버라이딩의 규칙

- 메서드 시그니처(이름, 매개변수, 반환 타입)가 부모 클래스와 동일해야 함
- 접근 제어자는 부모 클래스의 메서드보다 더 제한적이면 안 됨
- 예외는 부모 클래스 메서드의 예외와 같거나 더 좁은 범위여야 함

## 오버라이딩 예시 (Python)

```python
class Vehicle:
    def move(self):
        return "이동 중"

class Car(Vehicle):
    def move(self):
        return "도로 위를 달리는 중"

class Boat(Vehicle):
    def move(self):
        return "물 위를 항해하는 중"

# 객체 생성 및 메서드 호출
car = Car()
boat = Boat()
vehicle = Vehicle()

print(car.move())    # 출력: 도로 위를 달리는 중
print(boat.move())   # 출력: 물 위를 항해하는 중
print(vehicle.move()) # 출력: 이동 중
```

## 부모 클래스 메서드 호출

자식 클래스에서 오버라이딩된 메서드 내에서 부모 클래스의 메서드를 호출할 수 있음. 이를 통해 부모 클래스의 동작을 확장할 수 있음.

```python
class Bird:
    def sing(self):
        return "새소리"

class Parrot(Bird):
    def sing(self):
        base_sound = super().sing()
        return f"{base_sound} 그리고 앵무새 소리"

parrot = Parrot()
print(parrot.sing())  # 출력: 새소리 그리고 앵무새 소리
```

## Java에서의 오버라이딩 예시

```java
class Shape {
    public double getArea() {
        return 0;
    }
}

class Circle extends Shape {
    private double radius;

    public Circle(double radius) {
        this.radius = radius;
    }

    @Override
    public double getArea() {
        return Math.PI * radius * radius;
    }
}

class Rectangle extends Shape {
    private double width;
    private double height;

    public Rectangle(double width, double height) {
        this.width = width;
        this.height = height;
    }

    @Override
    public double getArea() {
        return width * height;
    }
}

public class Main {
    public static void main(String[] args) {
        Shape circle = new Circle(5);
        Shape rectangle = new Rectangle(4, 6);

        System.out.println("원의 면적: " + circle.getArea());
        System.out.println("직사각형의 면적: " + rectangle.getArea());
    }
}
```

오버라이딩은 OOP의 핵심 개념 중 하나로, 상속과 밀접하게 연관되어 있음. 이를 통해 클래스 계층 구조에서 동일한 메서드 이름을 유지하면서도 각 클래스의 특성에 맞는 구체적인 동작을 정의할 수 있음. 오버라이딩은 다형성을 실현하는 주요 메커니즘으로, 코드의 유연성과 확장성을 크게 향상시킴.

특히 프레임워크나 라이브러리 설계 시 오버라이딩은 중요한 역할을 함. 기본 동작을 제공하면서도 사용자가 필요에 따라 특정 동작을 커스터마이즈할 수 있게 해주기 때문임. 이는 "템플릿 메소드 패턴"과 같은 디자인 패턴의 기초가 되며, 유연하고 확장 가능한 소프트웨어 구조를 만드는 데 기여함.
