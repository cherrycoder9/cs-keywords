# 스택

스택(Stack)은 데이터를 순서대로 쌓아 올리는 자료구조로, 후입선출(LIFO, Last In First Out) 원칙을 따름. 즉, 가장 나중에 삽입된 데이터가 가장 먼저 삭제되는 구조임. 스택은 간단하면서도 강력한 자료구조로, 다양한 프로그래밍 문제와 알고리즘에서 활용됨.

## 스택의 주요 연산

- **push(item)**: 스택의 맨 위에 새로운 요소를 추가함.
- **pop()**: 스택의 맨 위 요소를 제거하고 반환함.
- **peek() 또는 top()**: 스택의 맨 위 요소를 제거하지 않고 반환함.
- **isEmpty()**: 스택이 비어있는지 확인함.
- **size()**: 스택의 현재 크기를 반환함.

## Python에서의 스택 구현

Python에서는 리스트를 사용하여 스택을 쉽게 구현할 수 있음.

```python
class Stack:
    def __init__(self):
        self.items = []

    def push(self, item):
        self.items.append(item)

    def pop(self):
        if not self.is_empty():
            return self.items.pop()
        raise IndexError("스택이 비어있습니다.")

    def peek(self):
        if not self.is_empty():
            return self.items[-1]
        raise IndexError("스택이 비어있습니다.")

    def is_empty(self):
        return len(self.items) == 0

    def size(self):
        return len(self.items)

# 스택 사용 예시
stack = Stack()
stack.push("A")
stack.push("B")
stack.push("C")

print(stack.pop())  # 출력: C
print(stack.peek()) # 출력: B
print(stack.size()) # 출력: 2
print(stack.is_empty()) # 출력: False
```

## Java에서의 스택 구현

Java에서는 `java.util.Stack` 클래스를 사용하거나, 직접 구현할 수 있음.

```java
import java.util.ArrayList;
import java.util.EmptyStackException;

class Stack<T> {
    private ArrayList<T> items;

    public Stack() {
        items = new ArrayList<>();
    }

    public void push(T item) {
        items.add(item);
    }

    public T pop() {
        if (isEmpty()) {
            throw new EmptyStackException();
        }
        return items.remove(items.size() - 1);
    }

    public T peek() {
        if (isEmpty()) {
            throw new EmptyStackException();
        }
        return items.get(items.size() - 1);
    }

    public boolean isEmpty() {
        return items.isEmpty();
    }

    public int size() {
        return items.size();
    }
}

public class Main {
    public static void main(String[] args) {
        Stack<String> stack = new Stack<>();
        stack.push("A");
        stack.push("B");
        stack.push("C");

        System.out.println(stack.pop());   // 출력: C
        System.out.println(stack.peek());  // 출력: B
        System.out.println(stack.size());  // 출력: 2
        System.out.println(stack.isEmpty()); // 출력: false
    }
}
```

## 스택의 실제 응용

1. **함수 호출 관리**: 프로그램의 실행 스택에서 함수 호출과 반환을 관리함.

2. **괄호 검사**: 프로그래밍 언어의 구문 분석에서 괄호의 짝을 맞추는 데 사용됨.

    ```python
    def is_balanced(s):
        stack = []
        opening = "({["
        closing = ")}]"
        pairs = {")": "(", "}": "{", "]": "["}
        
        for char in s:
            if char in opening:
                stack.append(char)
            elif char in closing:
                if not stack or stack.pop() != pairs[char]:
                    return False
        
        return len(stack) == 0

    # 사용 예시
    print(is_balanced("({[()]})"))  # 출력: True
    print(is_balanced("([)]"))      # 출력: False
    ```

3. **역순 출력**: 문자열이나 리스트의 요소를 역순으로 출력할 때 사용됨.

4. **웹 브라우저 방문 기록**: 웹 브라우저의 '뒤로 가기' 기능을 구현할 때 스택을 사용함.

5. **깊이 우선 탐색(DFS)**: 그래프나 트리의 깊이 우선 탐색 알고리즘에서 사용됨.

## 스택의 장단점

장점:

- 구현이 간단하고 직관적임.
- 데이터의 삽입과 삭제가 O(1) 시간 복잡도로 매우 빠름.
- 메모리를 효율적으로 사용할 수 있음.

단점:

- 크기가 제한적일 경우 스택 오버플로우 문제가 발생할 수 있음.
- 중간에 있는 데이터에 직접 접근할 수 없음.

스택은 간단하면서도 강력한 자료구조로, 많은 알고리즘과 시스템에서 중요한 역할을 함. 특히 재귀 알고리즘, 메모리 관리, 표현식 평가 등 다양한 분야에서 활용되며, 프로그래밍의 기본적인 개념을 이해하는 데 필수적인 자료구조임. 스택의 LIFO 특성을 잘 이해하고 활용하면 많은 프로그래밍 문제를 효율적으로 해결할 수 있음.
