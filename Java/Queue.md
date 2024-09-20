# Queue란?
큐(Queue)는 선입선출(FIFO: First In First Out) 원칙을 따르는 선형 자료구조이다. 큐에서 먼저 들어간 데이터가 먼저 나오는 방식으로 동작한다.

![image](https://github.com/user-attachments/assets/5356e7d9-debd-459e-9320-83569b552ee3)

## 주요 연산
- enqueue: 큐의 뒤쪽에 새로운 요소를 추가하는 연산
- dequeue: 큐의 앞쪽에 있는 요소를 제거하고 반환하는 연산
- peek: 큐의 앞쪽에 있는 요소를 제거하지 않고 반환하는 연산
- isEmpty: 큐가 비어있는지 확인하는 연산
- sizse: 큐에 들어 있는 요소의 개수를 반환하는 연산

<hr>
<br><br>

## Queue의 사용 예시
```Java
import java.util.LinkedList;
import java.util.Queue;

public class QueueExample {
    public static void main(String[] args) {
        Queue<Integer> queue = new LinkedList<>();

        // enqueue 연산
        queue.offer(10);
        queue.offer(20);
        queue.offer(30);

        // peek 연산
        System.out.println(queue.peek());  // 출력: 10

        // dequeue 연산
        System.out.println(queue.poll());  // 출력: 10
        System.out.println(queue.poll());  // 출력: 20

        // 큐가 비었는지 확인
        System.out.println("queue empty? " + queue.isEmpty());  // 출력: false
    }
}
```
자바에서 가장 많이 사용되는 구현클래스는 LinkedList 와 ArrayDeque가 있다.

## Queue의 활용
- 프린터 대기열
- 프로세스 스케줄링
- 데이터 스트리밍
- 레벨 순회

### 장점
- 선입선출 구조로, 순차적으로 작업을 처리하는 과정에서 효율적이다.
- 삽입, 삭제가 양쪽 끝에서만 이루어지기 때문에 구현이 간단함
### 단점
- 중간에 있는 요소 접근 불가
