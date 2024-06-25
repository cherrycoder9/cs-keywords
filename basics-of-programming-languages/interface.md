# 인터페이스

인터페이스(Interface)는 객체지향 프로그래밍(OOP)에서 클래스가 구현해야 하는 메서드의 명세를 정의하는 추상화 도구임. 인터페이스는 메서드의 시그니처만을 선언하고, 실제 구현은 이를 구현하는 클래스에서 제공함. 이를 통해 다양한 클래스가 동일한 인터페이스를 통해 상호작용할 수 있게 함.

## 인터페이스의 주요 특징

- **구현의 강제**: 인터페이스를 구현하는 클래스는 모든 선언된 메서드를 반드시 구현해야 함.
- **다형성 지원**: 동일한 인터페이스를 구현한 다양한 객체를 일관된 방식으로 다룰 수 있음.
- **유연성 제공**: 구현 클래스 간의 교체 가능성을 높여 시스템의 유연성을 향상시킴.
- **느슨한 결합**: 클래스 간의 의존성을 줄이고 모듈화를 촉진함.

## Java에서의 인터페이스 예시

```java
interface Drawable {
    void draw();
}

class Circle implements Drawable {
    @Override
    public void draw() {
        System.out.println("원을 그립니다.");
    }
}

class Rectangle implements Drawable {
    @Override
    public void draw() {
        System.out.println("사각형을 그립니다.");
    }
}

public class Main {
    public static void main(String[] args) {
        Drawable circle = new Circle();
        Drawable rectangle = new Rectangle();

        circle.draw();     // 출력: 원을 그립니다.
        rectangle.draw();  // 출력: 사각형을 그립니다.
    }
}
```

## Python에서의 인터페이스 구현

Python은 명시적인 인터페이스를 지원하지 않지만, 추상 기본 클래스(ABC)를 사용하여 유사한 기능을 구현할 수 있음.

```python
from abc import ABC, abstractmethod

class Playable(ABC):
    @abstractmethod
    def play(self):
        pass

    @abstractmethod
    def stop(self):
        pass

class Music(Playable):
    def play(self):
        print("음악을 재생합니다.")

    def stop(self):
        print("음악을 정지합니다.")

class Video(Playable):
    def play(self):
        print("동영상을 재생합니다.")

    def stop(self):
        print("동영상을 정지합니다.")

def use_media(media):
    media.play()
    media.stop()

music = Music()
video = Video()

use_media(music)
use_media(video)
```

## 인터페이스의 장점

1. **코드 일관성 유지**: 동일한 인터페이스를 구현한 클래스들은 일관된 방식으로 사용될 수 있음.
2. **유연성 향상**: 구현 클래스를 쉽게 교체할 수 있어 시스템의 유연성이 증가함.
3. **다형성 지원**: 다양한 구현체를 동일한 타입으로 처리할 수 있음.
4. **명확한 계약 정의**: 클래스가 구현해야 할 메서드를 명확히 정의하여 개발자 간 협업을 용이하게 함.
5. **모듈화 촉진**: 시스템을 독립적인 모듈로 나누어 개발할 수 있게 함.

## 인터페이스와 추상 클래스의 차이점

- **다중 구현**: Java에서 클래스는 여러 인터페이스를 구현할 수 있지만, 하나의 클래스만 상속받을 수 있음.
- **구현 여부**: 인터페이스는 메서드 선언만 포함하지만, 추상 클래스는 일부 메서드의 구현을 포함할 수 있음.
- **사용 목적**: 인터페이스는 '할 수 있는 것'을 정의하는 반면, 추상 클래스는 '어떤 것'을 정의함.

인터페이스는 객체지향 설계에서 중요한 역할을 함. 특히 의존성 주입(Dependency Injection)과 같은 디자인 패턴을 구현할 때 유용하게 사용됨. 인터페이스를 통해 시스템의 다양한 컴포넌트 간의 상호작용을 정의함으로써, 각 컴포넌트의 구체적인 구현에 대한 의존성을 줄이고 시스템의 유연성과 확장성을 높일 수 있음.

또한, 인터페이스는 API 설계에 있어서도 중요한 역할을 함. 잘 설계된 인터페이스는 사용자에게 필요한 기능만을 노출하고 구현 세부사항을 숨김으로써, 사용하기 쉽고 유지보수가 용이한 API를 제공할 수 있음. 이는 '정보 은닉' 원칙을 실현하는 또 다른 방법이며, 시스템의 복잡성을 관리하는 데 도움이 됨.
