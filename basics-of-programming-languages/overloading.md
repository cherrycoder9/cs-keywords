# 오버로딩

오버로딩(Overloading)은 객체지향 프로그래밍(OOP)에서 동일한 이름의 메서드나 연산자가 다양한 매개변수를 처리할 수 있도록 하는 기능임. 이를 통해 유사한 기능을 하는 메서드들을 하나의 이름으로 통합하여 코드의 일관성과 가독성을 높일 수 있음.

## 오버로딩의 주요 특징

- **다형성 구현**: 같은 이름으로 다양한 형태의 입력을 처리할 수 있음.
- **코드 간결성**: 유사한 기능을 하나의 메서드 이름으로 통합하여 코드를 간결하게 만듦.
- **유연성 증대**: 다양한 매개변수 조합으로 메서드를 호출할 수 있어 유연성이 높아짐.

## 메서드 오버로딩 예시 (Java)

Java에서는 메서드 오버로딩을 직접 지원함.

```java
public class Calculator {
    public int add(int a, int b) {
        return a + b;
    }

    public double add(double a, double b) {
        return a + b;
    }

    public int add(int a, int b, int c) {
        return a + b + c;
    }

    public String add(String a, String b) {
        return a + b;
    }

    public static void main(String[] args) {
        Calculator calc = new Calculator();
        System.out.println(calc.add(5, 3));           // 출력: 8
        System.out.println(calc.add(2.5, 3.7));       // 출력: 6.2
        System.out.println(calc.add(1, 2, 3));        // 출력: 6
        System.out.println(calc.add("Hello", "World")); // 출력: HelloWorld
    }
}
```

## Python에서의 오버로딩 구현

Python은 직접적인 메서드 오버로딩을 지원하지 않지만, 기본 매개변수나 가변 인자를 사용하여 유사한 기능을 구현할 수 있음.

```python
class Calculator:
    def add(self, *args):
        if all(isinstance(arg, (int, float)) for arg in args):
            return sum(args)
        elif all(isinstance(arg, str) for arg in args):
            return ''.join(args)
        else:
            raise TypeError("인자의 타입이 올바르지 않습니다.")

calc = Calculator()
print(calc.add(5, 3))           # 출력: 8
print(calc.add(2.5, 3.7))       # 출력: 6.2
print(calc.add(1, 2, 3))        # 출력: 6
print(calc.add("Hello", "World")) # 출력: HelloWorld
```

## 연산자 오버로딩 예시 (Python)

Python에서는 특별 메서드를 통해 연산자 오버로딩을 구현할 수 있음.

```python
class Vector:
    def __init__(self, x, y):
        self.x = x
        self.y = y

    def __add__(self, other):
        return Vector(self.x + other.x, self.y + other.y)

    def __str__(self):
        return f"Vector({self.x}, {self.y})"

v1 = Vector(2, 3)
v2 = Vector(3, 4)
v3 = v1 + v2
print(v3)  # 출력: Vector(5, 7)
```

## 오버로딩의 장점

1. **코드 가독성 향상**: 유사한 기능을 하는 메서드들을 하나의 이름으로 통합하여 코드를 더 읽기 쉽게 만듦.
2. **유연성 증대**: 다양한 타입과 개수의 매개변수를 처리할 수 있어 더 유연한 코드 작성이 가능함.
3. **직관적인 인터페이스**: 사용자가 메서드나 연산자를 직관적으로 사용할 수 있게 함.
4. **코드 재사용성**: 동일한 기능을 여러 형태로 재사용할 수 있어 코드 중복을 줄임.

오버로딩은 객체지향 프로그래밍의 중요한 특성 중 하나인 다형성을 구현하는 방법임. 이를 통해 같은 이름의 메서드나 연산자가 다양한 상황에서 적절하게 동작할 수 있게 되어, 코드의 일관성과 표현력을 높일 수 있음.

특히 메서드 오버로딩은 클래스의 인터페이스를 더 직관적이고 사용하기 쉽게 만듦. 예를 들어, 문자열 연결, 숫자 더하기, 리스트 연결 등 다양한 타입의 '덧셈' 연산을 모두 `add` 메서드로 통일할 수 있어, 사용자가 쉽게 이해하고 사용할 수 있는 API를 설계할 수 있음.

연산자 오버로딩은 사용자 정의 객체에 대해 기본 연산자의 동작을 재정의할 수 있게 해주어, 복잡한 객체를 더 자연스럽고 직관적으로 다룰 수 있게 함. 이는 특히 수학적 객체나 데이터 구조를 다룰 때 유용함.
