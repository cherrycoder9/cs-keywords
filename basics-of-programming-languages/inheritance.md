# 상속

상속은 객체지향 프로그래밍(OOP)에서 기존 클래스의 속성과 메서드를 새로운 클래스가 물려받는 메커니즘임. 코드 재사용성을 높이고 클래스 간 계층 구조를 정의하는 데 사용됨.

## 상속의 기본 개념

- **부모 클래스**: 속성과 메서드를 물려주는 클래스. 슈퍼클래스라고도 함.
- **자식 클래스**: 부모 클래스의 속성과 메서드를 물려받는 클래스. 서브클래스라고도 불림.

## 상속의 목적

- 코드 재사용성 증대
- 구조적인 시스템 설계 가능
- 유지보수성 향상

## 상속의 구현

```python
class Vehicle:
    def __init__(self, make, model, year):
        self.make = make
        self.model = model
        self.year = year

    def start_engine(self):
        return "엔진 시동"

class Car(Vehicle):
    def __init__(self, make, model, year, doors):
        super().__init__(make, model, year)
        self.doors = doors

    def honk_horn(self):
        return "빵빵!"

my_car = Car("현대", "쏘나타", 2023, 4)
print(my_car.start_engine())  # 출력: 엔진 시동
print(my_car.honk_horn())     # 출력: 빵빵!
```

## 메서드 오버라이딩

자식 클래스에서 부모 클래스의 메서드를 재정의하는 기능. 같은 이름의 메서드를 자식 클래스의 필요에 맞게 변경할 수 있음.

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

dog = Dog()
cat = Cat()
print(dog.speak())  # 출력: 멍멍!
print(cat.speak())  # 출력: 야옹!
```

## 다중 상속

한 클래스가 두 개 이상의 부모 클래스로부터 상속받는 기능. 여러 클래스의 특성을 결합할 수 있지만, 복잡성이 증가할 수 있어 주의가 필요함.

```python
class Flyer:
    def fly(self):
        return "날기"

class Swimmer:
    def swim(self):
        return "수영하기"

class FlyingFish(Flyer, Swimmer):
    pass

flying_fish = FlyingFish()
print(flying_fish.fly())   # 출력: 날기
print(flying_fish.swim())  # 출력: 수영하기
```

상속은 OOP의 핵심 개념 중 하나로, 코드의 재사용성을 높이고 프로그램을 체계적으로 구조화하는 데 중요한 역할을 함. 이를 통해 클래스 간의 관계를 명확히 정의하고, 공통된 특성을 효율적으로 관리할 수 있음. 다만, 과도한 상속 계층은 코드의 복잡성을 증가시킬 수 있으므로, 적절한 설계와 사용이 중요함.

상속을 활용하면 기존 코드를 확장하고 수정하는 데 드는 시간과 노력을 줄일 수 있으며, 코드의 일관성과 유지보수성을 향상시킬 수 있음. 또한, 다형성과 결합하여 더욱 유연하고 확장 가능한 프로그램 구조를 만들 수 있음.
