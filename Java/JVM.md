# JVM (Java Virtual Machine)
JVM (Java Virtual Machine)은 자바 애플리케이션을 실행하기 위한 가상 머신으로 하드웨어나 운영체제와 무관하게 자바 프로그램이 동작할 수 있도록 해주는 중요한 역할이다.
> JVM은 다양한 플랫폼에 설치되어, 동일한 자바 프로그램이 어떤 환경에서도 동일하게 실행될 수 있게 해준다.

<hr>
<br><br>

## JVM의 주요 역할
### 1. 바이트코드 실행
- 자바 컴파일러(javac)는 자바 소스 코드를 바이트코드(.class파일)로 변환
- 운영체제에서 이해할 수 있는 기계어로 변환하여 실행하는 작업을 담당

### 2. 메모리 관리
- JVM은 프로그램 실행 중 메모리 관리를 자동으로 처리한다. 주로 Queue, Stack 메모리로 나뉘며, 객체의 생성과 제거를 담당함
- Garbage Collection(가비지 컬렉션)을 통해 더 이상 사용되지 않는 객체를 자동으로 메모리에서 해제하여 메모리 누수를 방지한다.

### 3. 플랫폼 독립성 제공
- 자바 애플리케이션은 운영체제에 종속되지 않으며, 바이트코드로 컴파일된 후 JVM이 설치된 모든 운영체제에서 실행될 수 있음

### 4. 런타임 환경 제공
- JVM은 자바 애플리케이션을 실행하기 위해 필요한 런타임 환경을 제공한다. 이 환경에는 스레드 관리, 예외처리, 보안 관리 등이 포함되어 있음

<hr>
<br><br>

## JVM 구조와 작동 원리

![image](https://github.com/user-attachments/assets/d0ba2344-bbb9-4db9-8829-66102610f9c6)

### JVM의 구조
- Class Loader : 클래스 파일을 Runtime Data Area의 메서드 영역으로 불러오는 역할을 한다.
- Runtime Data Area : 런타임 시 클래스 데이터와 같은 메타 데이터가 저장되는 곳 (OS로부터 할당 받은 메모리 영역)
- Execution Engine : .class파일과 같은 ByteCode를 실행 가능하도록 해석한다.
- GC : 메모리 관리 기법 중 하나로, Heap 영역에 배치된 객체들을 관리하는 모듈
> Runtime Data Area은 Method Area, Heap, PC Registers, Java Stacks, Native Method Stacks로 나누어진다.
