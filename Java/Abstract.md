# Abstract Class
Abstract(추상 클래스)는 객체를 직접 생성할 수 없는 클래스로, 하나 이상의 추상 메소드를 포함할 수 있다. 하위 클래스가 반드시 상속 받아 구현해야 할 메소드를 정의하고, 일부는 구현을 제공할 수 있음

## 특징
### 1. 추상 메소드를 포함할 수 있음
```java
abstract class Animal {
    abstract void sound(); // 추상 메소드, 하위 클래스에서 구현 필요
}
```
추상 메소드는 구현부가 없는 메소드로, 해당 클래스를 상속받는 자식 클래스가 구체적인 구현을 제공해야 한다.

<br>

### 2. 일반 메소드와 필드를 포함할 수 있음
```java
abstract class Animal {
    String name;
    
    void eat() { // 일반 메소드
        System.out.println(name + " is eating");
    }
    
    abstract void sound(); // 추상 메소드
}
```
추상 클래스는 일반 메소드와 필드를 포함할 수 있다. 이는 자식 클래스에서 공통으로 사용할 수 있는 기능을 제공할 수 있음

<br>

### 3. 객체 생성 불가
```java
Animal a = new Animal(); // 오류 발생: 추상 클래스는 객체 생성 불가
```
추상 클래스는 new 키워드를 사용해 추상 클래스를 객체로 만들 수 없다. 반드시 상속을 통해 자식 클래스에서 구현한 후에 인스턴스를 만들 수 있음

<br>

### 4. 상속을 통해 사용
```java
class Dog extends Animal {
    @Override
    void sound() { // 추상 메소드 구현
        System.out.println("Bark");
    }
}

Dog dog = new Dog();
dog.sound(); // 출력: Bark
```
추상 클래스는 다른 클래스가 상속받아 사용할 수 있음. 자식 클래스는 추상 클래스에서 선언된 추상 메소드를 구체적으로 구현해야 한다.

<br>

### 5. 다중 상속 불가
자바에서 클래스 상속은 단일 상속만 가능하기 때문에, 하나의 추상 클래스만 상속할 수 있다.
> 인터페이스는 다중 상속이 가능

<hr>
<br><br>

## 예시
```java
// 추상 클래스 정의
abstract class Animal {
    String name;

    // 일반 메소드
    void eat() {
        System.out.println(name + " is eating");
    }

    // 추상 메소드
    abstract void sound();
}

// 추상 클래스를 상속하는 하위 클래스
class Dog extends Animal {
    // 추상 메소드 구현
    @Override
    void sound() {
        System.out.println("Bark");
    }
}

class Cat extends Animal {
    // 추상 메소드 구현
    @Override
    void sound() {
        System.out.println("Meow");
    }
}

public class Main {
    public static void main(String[] args) {
        Dog dog = new Dog();
        dog.name = "Buddy";
        dog.eat();  // 출력: Buddy is eating
        dog.sound(); // 출력: Bark

        Cat cat = new Cat();
        cat.name = "Kitty";
        cat.eat();  // 출력: Kitty is eating
        cat.sound(); // 출력: Meow
    }
}

```
