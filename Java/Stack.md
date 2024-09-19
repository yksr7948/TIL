# Stack이란?
스택(Stack)은 후입선출(LIFO: Last In, First Out) 구조를 따르는 선형 자료구조 이다. 즉, 마지막에 추가된 요소가 가장 먼저 제거되는 구조를 가지고 있음

스택은 주로 데이터의 순서가 중요할 때 사용되며, 여러 프로그래밍 언어에서 기본 자료구조로 제공된다.

![image](https://github.com/user-attachments/assets/98d548ad-0ae9-451a-809b-0df29d9f5f3f)

## Stack의 주요 연산
- push : 스택의 맨 위에 새로운 요소를 추가하는 연산
- pop : 스택이 맨 위에 있는 요소를 제거하고 반환하는 연산
- peek(top) : 스택의 맨 위에 있는 요소를 제거하지 않고 반환하는 연산 
- isEmpty : 스택이 비어 있는지 확인하는 연산(비어있으면 true를 반환함)
- size : 스택에 들어 있는 요소의 개수를 반환하는 연산

<hr>
<br><br>

## Stack 사용 예시
```Java
import java.util.Stack;

public class StackExample {
    public static void main(String[] args) {
        Stack<Integer> stack = new Stack<>();

        // push 연산
        stack.push(10);
        stack.push(20);
        stack.push(30);

        // peek 연산
        System.out.println("첫 번째: " + stack.peek());  // 출력: 30

        // pop 연산
        System.out.println("두 번째: " + stack.pop());  // 출력: 30
        System.out.println("세 번째: " + stack.pop());  // 출력: 20

        // 스택이 비었는지 확인
        System.out.println("Is stack empty? " + stack.isEmpty());  // 출력: false
    }
}
```

### Stack 장점
- 후입선출(LIFO) 원칙에 따라 간단하게 구현하고 사용
- 재귀적 문제나 탐색 문제를 해결
- 함수 호출 시 스택 프레임을 관리하여 효율적으로 메모리 사용
### Stack 단점
- 스택이 넘칠 경우, StackOverflowError가 발생
- 스택의 구조상, 중간에 있는 요소에 직접 접근할 수 없고, 오직 맨 위의 요소에만 접근할 수 있음



