# Overloding(오버로딩)
## 정의
자바에서의 오버로딩은 같은 이름을 가진 메서드를 여러 개 정의할 수 있는 기능을 말한다.
> 같은 메서드 이름을 사용하되, 매개변수의 타입, 개수, 순서 등을 다르게 하여 메서드를 여러 개 정의하는 방식

## 오버로딩의 특징
- 매서드의 이름이 동일해야 됨
- 매개변수의 목록이 달라야됨(개수, 타입, 순서...)
- 메서드의 반환 타입은 오버로딩과 관계가 없음

## 예시
```Java
public class Calculator {

    // 두 개의 정수를 더하는 메서드
    public int add(int a, int b) {
        return a + b;
    }

    // 세 개의 정수를 더하는 메서드 (매개변수 개수가 다름)
    public int add(int a, int b, int c) {
        return a + b + c;
    }

    // 두 개의 실수를 더하는 메서드 (매개변수 타입이 다름)
    public double add(double a, double b) {
        return a + b;
    }

    // 두 개의 정수와 하나의 실수를 더하는 메서드 (매개변수 타입 및 순서가 다름)
    public double add(int a, double b, int c) {
        return a + b + c;
    }
}
```
위 코드에서는 add라는 이름의 메서드가 여러개 정의 되어 있지만, 각각의 매서드는 매개변수의 개수, 타입, 순서가 다르므로 오버로딩이 성립이 된다

이를 통해 코드의 재사용성과 유연성이 높아짐
