# 힙

힙(Heap)은 완전 이진 트리(Complete Binary Tree) 구조를 기반으로 하는 특수한 자료구조로, 주로 우선순위 큐(Priority Queue)를 구현하는 데 사용됨. 힙은 최대 힙(Max Heap)과 최소 힙(Min Heap) 두 가지 형태로 존재하며, 각각 부모 노드가 자식 노드보다 크거나 같은 값을 가지거나(최대 힙), 작거나 같은 값을 가짐(최소 힙).

## 힙의 주요 특징

- **완전 이진 트리**: 마지막 레벨을 제외한 모든 레벨이 완전히 채워져 있으며, 마지막 레벨은 왼쪽부터 차례대로 채워짐.
- **힙 속성**: 최대 힙에서는 부모 노드가 자식 노드보다 크거나 같고, 최소 힙에서는 부모 노드가 자식 노드보다 작거나 같음.
- **효율적인 삽입 및 삭제**: 최솟값 또는 최댓값을 O(log n) 시간 복잡도로 찾을 수 있음.

## 힙의 주요 연산

1. **삽입 (Insertion)**: 새 요소를 힙의 마지막에 추가하고, 힙 속성을 만족할 때까지 위로 이동시킴.
2. **삭제 (Deletion)**: 루트 노드(최솟값 또는 최댓값)를 제거하고, 마지막 요소를 루트로 이동시킨 후, 힙 속성을 만족할 때까지 아래로 이동시킴.
3. **힙 구성 (Heapify)**: 주어진 배열을 힙 구조로 변환함.

## Python에서의 힙 구현

Python은 `heapq` 모듈을 통해 최소 힙을 기본적으로 제공함.

```python
import heapq

class MinHeap:
    def __init__(self):
        self.heap = []

    def push(self, item):
        heapq.heappush(self.heap, item)

    def pop(self):
        if self.heap:
            return heapq.heappop(self.heap)
        return None

    def peek(self):
        if self.heap:
            return self.heap[0]
        return None

# 사용 예시
min_heap = MinHeap()
min_heap.push(3)
min_heap.push(1)
min_heap.push(4)
min_heap.push(2)

print(min_heap.pop())  # 출력: 1
print(min_heap.pop())  # 출력: 2
print(min_heap.peek()) # 출력: 3
```

## Java에서의 힙 구현

Java에서는 `PriorityQueue` 클래스를 사용하여 힙을 구현할 수 있음.

```java
import java.util.PriorityQueue;

public class MaxHeap<T extends Comparable<T>> {
    private PriorityQueue<T> heap;

    public MaxHeap() {
        heap = new PriorityQueue<>((a, b) -> b.compareTo(a));
    }

    public void push(T item) {
        heap.offer(item);
    }

    public T pop() {
        return heap.poll();
    }

    public T peek() {
        return heap.peek();
    }

    public boolean isEmpty() {
        return heap.isEmpty();
    }

    public static void main(String[] args) {
        MaxHeap<Integer> maxHeap = new MaxHeap<>();
        maxHeap.push(3);
        maxHeap.push(1);
        maxHeap.push(4);
        maxHeap.push(2);

        System.out.println(maxHeap.pop());  // 출력: 4
        System.out.println(maxHeap.pop());  // 출력: 3
        System.out.println(maxHeap.peek()); // 출력: 2
    }
}
```

## 힙의 응용

1. **우선순위 큐**: 작업 스케줄링, 이벤트 관리 등에서 우선순위가 높은 항목을 빠르게 추출할 수 있음.

2. **힙 정렬 (Heap Sort)**: 힙을 사용하여 O(n log n) 시간 복잡도의 정렬 알고리즘을 구현할 수 있음.

    ```python
    def heapify(arr, n, i):
        largest = i
        left = 2 * i + 1
        right = 2 * i + 2

        if left < n and arr[largest] < arr[left]:
            largest = left

        if right < n and arr[largest] < arr[right]:
            largest = right

        if largest != i:
            arr[i], arr[largest] = arr[largest], arr[i]
            heapify(arr, n, largest)

    def heap_sort(arr):
        n = len(arr)

        # 최대 힙 구성
        for i in range(n // 2 - 1, -1, -1):
            heapify(arr, n, i)

        # 힙에서 요소를 하나씩 꺼내어 정렬
        for i in range(n - 1, 0, -1):
            arr[0], arr[i] = arr[i], arr[0]
            heapify(arr, i, 0)

    # 사용 예시
    arr = [12, 11, 13, 5, 6, 7]
    heap_sort(arr)
    print(arr)  # 출력: [5, 6, 7, 11, 12, 13]
    ```

3. **최단 경로 알고리즘**: 다익스트라 알고리즘과 같은 최단 경로 알고리즘에서 힙을 사용하여 효율성을 높일 수 있음.

4. **메디안 찾기**: 두 개의 힙(최대 힙과 최소 힙)을 사용하여 스트림에서 실시간으로 중앙값을 찾을 수 있음.

## 힙의 장단점

장점:

- 최댓값 또는 최솟값을 빠르게 찾을 수 있음 (O(1) 시간 복잡도).
- 삽입과 삭제 연산이 효율적임 (O(log n) 시간 복잡도).
- 우선순위 큐 구현에 적합함.

단점:

- 특정 요소를 검색하는 데 O(n) 시간이 걸림.
- 힙 속성을 유지하기 위해 추가적인 연산이 필요함.

힙은 효율적인 우선순위 관리와 정렬에 유용한 자료구조로, 다양한 알고리즘과 시스템에서 중요한 역할을 함. 특히 실시간 시스템, 데이터 스트림 처리, 그래프 알고리즘 등에서 널리 사용되며, 대규모 데이터 처리에서도 효과적으로 활용됨.
