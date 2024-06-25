# 제네릭

제네릭(Generics)은 데이터 타입을 일반화하여 다양한 타입을 효과적으로 처리할 수 있게 하는 프로그래밍 기법임. 이를 통해 코드의 재사용성을 높이고, 타입 안정성을 보장하며, 더 유연한 프로그래밍이 가능해짐.

## 제네릭의 주요 특징

- **타입 안정성**: 컴파일 시점에 타입 체크를 수행하여 런타임 오류를 방지함.
- **코드 재사용성**: 다양한 타입에 대해 동일한 로직을 적용할 수 있어 코드 중복을 줄임.
- **가독성 향상**: 명시적인 타입 지정으로 코드의 의도를 명확히 전달할 수 있음.
- **유연성**: 다양한 데이터 타입을 처리할 수 있는 유연한 코드 작성이 가능함.

## Java에서의 제네릭 사용 예시

### 제네릭 클래스

```java
public class Pair<K, V> {
    private K key;
    private V value;

    public Pair(K key, V value) {
        this.key = key;
        this.value = value;
    }

    public K getKey() { return key; }
    public V getValue() { return value; }

    public void setKey(K key) { this.key = key; }
    public void setValue(V value) { this.value = value; }

    @Override
    public String toString() {
        return "(" + key + ", " + value + ")";
    }

    public static void main(String[] args) {
        Pair<String, Integer> pair1 = new Pair<>("Age", 30);
        Pair<Double, String> pair2 = new Pair<>(3.14, "PI");

        System.out.println(pair1);  // 출력: (Age, 30)
        System.out.println(pair2);  // 출력: (3.14, PI)
    }
}
```

### 제네릭 메서드

```java
public class GenericMethods {
    public static <T extends Comparable<T>> T findMax(T a, T b) {
        return a.compareTo(b) > 0 ? a : b;
    }

    public static void main(String[] args) {
        System.out.println(findMax(10, 20));  // 출력: 20
        System.out.println(findMax("apple", "banana"));  // 출력: banana
    }
}
```

## C++에서의 템플릿 사용 예시

C++에서는 템플릿(Template)을 사용하여 제네릭 프로그래밍을 구현함.

### 함수 템플릿

```cpp
#include <iostream>
#include <string>

template <typename T>
T findMax(T a, T b) {
    return (a > b) ? a : b;
}

int main() {
    std::cout << findMax(10, 20) << std::endl;  // 출력: 20
    std::cout << findMax(3.14, 2.72) << std::endl;  // 출력: 3.14
    std::cout << findMax<std::string>("apple", "banana") << std::endl;  // 출력: banana

    return 0;
}
```

### 클래스 템플릿

```cpp
#include <iostream>
#include <string>

template <typename T>
class Stack {
private:
    static const int MAX_SIZE = 100;
    T data[MAX_SIZE];
    int top;

public:
    Stack() : top(-1) {}

    void push(T item) {
        if (top < MAX_SIZE - 1) {
            data[++top] = item;
        }
    }

    T pop() {
        if (top >= 0) {
            return data[top--];
        }
        throw std::out_of_range("Stack is empty");
    }

    bool isEmpty() const {
        return top == -1;
    }
};

int main() {
    Stack<int> intStack;
    intStack.push(10);
    intStack.push(20);
    std::cout << intStack.pop() << std::endl;  // 출력: 20

    Stack<std::string> stringStack;
    stringStack.push("Hello");
    stringStack.push("World");
    std::cout << stringStack.pop() << std::endl;  // 출력: World

    return 0;
}
```

## 제네릭의 장점

1. **타입 안정성 보장**: 컴파일 시점에 타입 검사를 수행하여 런타임 오류를 방지함.
2. **코드 재사용성 증가**: 동일한 로직을 다양한 타입에 적용할 수 있어 코드 중복을 줄임.
3. **성능 향상**: 타입 캐스팅이 필요 없어 실행 시 성능이 향상됨.
4. **알고리즘 일반화**: 특정 타입에 종속되지 않는 일반화된 알고리즘 구현이 가능함.
5. **컬렉션 프레임워크 강화**: 제네릭을 통해 타입 안전한 컬렉션 사용이 가능함.

제네릭은 현대 프로그래밍에서 필수적인 개념으로, 코드의 재사용성과 타입 안정성을 크게 향상시킴. 특히 대규모 소프트웨어 개발에서 제네릭의 사용은 코드의 품질과 유지보수성을 높이는 데 중요한 역할을 함.

제네릭을 효과적으로 사용하기 위해서는 타입 매개변수의 적절한 사용, 와일드카드의 이해, 타입 경계 설정 등 고급 개념에 대한 이해가 필요함. 이를 통해 더욱 유연하고 강력한 프로그래밍이 가능해짐.
