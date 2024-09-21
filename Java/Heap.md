# Heap 이란?
Heap(힙)은 이진 트리 형태를 가진 <code>완전 이진 트리</code>의 일종으로, 우선순위 큐 를 구현하는 데 많이 사용되는 자료구조이다.


## Heap의 종류
- 최대 힙(Max Heap) : 부모노드가 자식노드보다 항상 크거나 같은 값을 가진다.
- 최소 힙(Min Heap) : 부모노드가 자식노드보다 항상 작거나 같은 값을 가진다.

![image](https://github.com/user-attachments/assets/6ba76f77-2878-4562-b4cb-61ab998e020b)

## Heap의 특성
- 힙은 완전 이진 트리의 구조를 가지며, 노드가 왼쪽부터 차례대로 채워진다.(완전 이진 트리)
- 부모-자식 관계를 가짐

## Heap의 주요 연산
- insert
- remove
- peek

<hr>
<br><br>

## Heap 구현
```Java
import java.util.PriorityQueue;

public class MinHeapExample {
    public static void main(String[] args) {
        PriorityQueue<Integer> minHeap = new PriorityQueue<>();

        // 힙에 요소 삽입
        minHeap.offer(10);
        minHeap.offer(15);
        minHeap.offer(20);
        minHeap.offer(17);
        minHeap.offer(25);

        // 최소값 확인 (최소 힙이므로 가장 작은 값 반환)
        System.out.println("Min value: " + minHeap.peek());  // 출력: 10

        // 힙에서 요소 삭제 (가장 작은 값부터 삭제됨)
        while (!minHeap.isEmpty()) {
            System.out.println(minHeap.poll());  // 출력: 10, 15, 17, 20, 25
        }
    }
}
```
자바에서는 힙을 구현하기 위해 <code>PriorityQueue</code> 클래스를 사용해야된다. 기본적으로 <code>PriorityQueue</code>는 최소 힙으로 동작하며, 최대 힙을 구현하려면 사용자 정의인 <code>Comparator</code>를 사용해야된다.
> ex). PriorityQueue<Integer> maxHeap = new PriorityQueue<>(Collections.reverseOrder());


## 장점
- 빠른 우선순위 처리
- 메모리 효율성

## 단점
- 정렬된 상태가 아님
- 복잡한 구현
