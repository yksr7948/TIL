# Overriding(오버라이딩)
## 정의
Overriding(오버라이딩)은 상속과 관련된 개념으로, 자식 클래스가 부모 클래스의 매서드를 재정의 하는 것을 말한다.<br> 
상위 클래스에서 상속받은 매서드를 하위 클래스에서 동일한 이름, 매개변수, 반환 타입으로 다시 정의하여, 자식클래에서 부모 클래스의 매서드를 덮어쓰고 자신의 방식으로 동작하는 방식

## 조건
- 매서드 이름이 부모 클래스와 동일해야 된다.
- 매개변수 목록이 부모 클래스의 매서드와 동일해야 됨
- 반환 타입도 부모 클래스와 동일 해야 됨
- 접근 제한자는 부모 클래스의 매서드보다 좁은 범위로 설정 할 수 없음
  > ex). 부모 클래스가 public 이면 자식도 private가 될 수 없음

<hr>
<br><br>

## 오버라이딩 예시
```java
class Animal {
    // 부모 클래스의 메서드
    public void sound() {
        System.out.println("동물이 소리를 냅니다");
    }
}

class Dog extends Animal {
    // 부모 클래스의 메서드를 오버라이딩
    @Override
    public void sound() {
        System.out.println("강아지가 멍멍 소리를 냅니다");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal myAnimal = new Animal();  // 부모 클래스 객체
        myAnimal.sound();  // 출력: 동물이 소리를 냅니다

        Animal myDog = new Dog();  // 자식 클래스 객체
        myDog.sound();  // 출력: 강아지가 멍멍 소리를 냅니다 (오버라이딩된 메서드 호출)
    }
}
```
위 코드에서, Dog클래스는 부모 클래스인 Animal의 sound() 메소드를 오버라이딩 하여 자신의 방식으로 재정의 하였음

## ⭐ 오버라이딩과 @Override 어노테이션
- @Override 어노테이션은 자바에서 오버라이딩된 메서드임을 명시적으로 나타내기 위한 어노테이션이다.
- 이 어노테이션을 사용하면 컴파일러가 오버라이딩 규칙을 검증해주기 때문에, 실수로 매서드 이름이나 매개변수 목록을 잘못 정의한 경우 오류를 쉽게 잡아낼 수 있음

```java
@Override
public void sound() {
    System.out.println("강아지가 멍멍 소리를 냅니다");
}
```

## 오버라이딩의 목적
- 다형성
- 재사용성
- 유연성

<br><br>
## ⭐ 오버로딩(Overloding)과 오버라이딩(Overriding)의 차이점
|구분|오버로딩(Overloding)|오버라이딩(Overriding)|
|------|---|---|
|의미|같은 이름의 메서드를 매개변수 목록을 다르게 정의|상속받은 부모 클래스의 메서드를 재정의|
|클래스 관계|같은 클래스 내에서 발생|상속 관계에서 발생|
|매개변수 목록|다르게 정의 가능|부모와 동일해야 함|
|반환 타입|상관없음|부모와 동일해야 함|
|실행 시점|컴파일 시점|런타임 시점 (다형성)|
