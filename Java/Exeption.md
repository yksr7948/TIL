# Exception (예외처리)

## 📃 정의
예외처리란 프로그램 실행 중에 발생할 수 있는 오류(예외)를 적절하게 처리하여 프로그램이 비정상적으로 종료되지 않도록 하는 프로그래밍 기법이다.

예외는 개발자가 의도하지 않은 상황에서 발생하는 오류이며, 이러한 오류를 관리하지 않으면 프로그램이 중단될 수 있으므로 꼭 핋요한 작업이다.

## 🌼 예외처리의 목적
- 오류가 발생해도 프로그램이 중단되지 않고 계속 실핼될 수 있도록 함(프로그램의 안정성 유지)
- 오류가 발생한 부분에서 적절한 대처를 통해 복구하거나 대체 로직을 수행함(오류 복구)
- 발생한 오류에 대한 구체적인 디버깅을 제공해 오류를 쉽게 추적할 수 있다.

<hr>
<br><br>

## 🔥 예외처리의 종류
예외처리는 크게 두 종류가 있다.
- 1.&nbsp;&nbsp;Try-catch
- 2.&nbsp;&nbsp;throws

<br>

### 🔥 1. Try-catch문
Try-catch문은 메소드 내에 작성되며 예외가 발생할 수 있는 코드는 <code>try블록</code>에 작성하고 예외에 대한 처리를 <code>catch블록</code>에서 처리하는 구조이다.

```Java
try {
    // 예외가 발생할 가능성이 있는 코드
} catch (ExceptionType e) {
    // 예외가 발생했을 때 처리할 코드
}
```
### ⭐ 작동 방식
1. <code>try블록</code>
- 이 블록 안에 있는 코드를 실행
- 만약 이 블록 안에 예외가 발생하면 <code>try블록</code>의 나머지 코드는 실행되지 않고 즉시 <code>catch블록</code>으로 넘어간다.
- 예외가 발생하지 않으면 <code>try블록</code>이 정상적으로 완료되고 <code>catch블록</code>은 실행되지 않는다.

2. <code>catch블록</code>
- <code>try블록</code>에서 예외가 발생하면, 그 예외를 받아 처리함
- <code>catch블록</code>은 오류에 대한 정보를 인수로 받아서 예외 상황에 맞는 코드를 실해한다.
- 예외가 없으면 실행되지 않음
```Java
public class Main {
    public static void main(String[] args) {
        try {
            int result = 10 / 0;  // 0으로 나누는 예외 발생
            System.out.println("결과: " + result);
        } catch (ArithmeticException e) {
            System.out.println("예외 발생");
        }
    }
}
```
위 코드처럼 0으로 나누는 연산에서 <code>ArithmeticException</code> 발생하고, catch블록에서 그 예외를 처리해 프로그램이 비정상적으로 종료되지 않도록 함

<br>

### 🔥 2. throws
throws는 메소드가 특정 예외를 던질 가능성이 있다는 것을 명시적으로 선언할 때 사용한다. 메소드를 호출하는 호출자가 예뢰를 처리해야 한다.

```Java
public void test() throws IOException {
  메소드 내용...
}
```

### ⭐ throws가 하는 일
- 메소드 내에서 발생할 수 있는 예외를 호출자에게 알림
- 메소드 내부에서 발생한 예외를 직접 처리하지 않고 호출한 쪽으로 예외를 던질 수 있도록 허용
- <code>throws</code>는 <strong>검사된 예외(Checked Exception)</strong>에서 주로 사용된다.
