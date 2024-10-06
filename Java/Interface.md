# Interface
인터페이스(Interface)는 객체 지향 프로그래밍에서 클래스들 간에 공통된 동작을 정의하는 일종의 계약이나 약속이다. 
인터페이스는 클래스가 반드시 구현해야 하는 메서드의 집합을 정의하며, 구체적인 구현 내용은 포함하지 않고 메서드의 이름과 매개변수, 반환 타입만 정의한다.

## 특징
- 메서드의 선언만 포함하고 구현은 하지 않는다.
- 다중 상속을 지원함(상속과는 다름)
- 생성자 사용 불가
- 메서드 오버라이딩 필수

<br>

## 인터페이스 예시
```java
// 인터페이스 선언
public interface Animal {
    void sound(); // 메서드 선언만 존재
    void move();
}

// 인터페이스를 구현하는 클래스
public class Dog implements Animal {
    @Override
    public void sound() {
        System.out.println("Bark");
    }

    @Override
    public void move() {
        System.out.println("Run");
    }
}

// 인터페이스 사용
public class Main {
    public static void main(String[] args) {
        Animal dog = new Dog();  // 다형성
        dog.sound(); // "Bark"
        dog.move();  // "Run"
    }
}
```

## 장점
1. 다형성 : 같은 인터페이스를 구현한 객체들은 동일한 메서드를 가지고 있으므로, 코드 재사용성과 유연성이 높아짐
2. 코드 확장성 : 클래스와 클래스 간 결합도를 낮추어 유지보수가 쉬워짐
3. 유연한 설계 : 인터페이스는 구체적인 클래스에 의존하지 않기 때문에 구현체를 변경하거나 새로운 구현체를 추가하기 쉬워짐

## 인터페이스와 추상 클래스의 차이점
- 인터페이스는 오직 메소드만 선안할 수 있고 상태는 가질 수 없다.
- 추상클래스는 일부 메소드를 구현할 수 있으며, 상태를 가질 수 있다.
