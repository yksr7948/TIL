# AOP
AOP(Aspect-Oriented Programming) 관점 지향 프로그래밍은 소프트웨어 개발에서 핵심 비즈니스 로직과 부가적인 관심사를 분리하여 모듈화하는 프로그래밍 기법이다.

즉, 공통적으로 반복되는 부가 기능을 코드에 분리해서 적용함으로써, 핵심 로직에 영향을 주지 않고도 기능을 확장할 수 있게 한다.
> 이러한 부가 기능을 <strong>횡단 관심사</strong>라고 한다.

## AOP의 주요 개념
1. Aspect: 횡단 관심사를 모듈화한 것이다. 주로 Advice와 Pointcut으로 구성됨. 예를 들어, 로깅이나 보안 기능을 구현한 코드를 Aspect로 분리할 수 있음
2. Advice: 실제로 수행되는 횡단 관심사 코드다. 언제, 어떻게 횡단 관심사를 적용할지를 정의한다.
   - Before Advice: 핵심 비즈니스 로직이 실행되기 전에 실행된다.
   - After Advice: 핵심 로직이 완료된 후에 실행된다.
   - Around Advice: 핵심 로직 실행 전후에 실행되며, 핵심 로직 자체의 실행 여부도 제어할 수 있음
   - After Returning Advice: 핵심 로직이 정상적으로 실행된 후에 실행된다.
   - After Throwing Advice: 예외가 발생된 후에 실행된다.
3. Join Point: 핵심 로직이 실행되는 시점.
4. Pointcut: Advice가 적용될 Join Point를 정의하는 표현식. AOP가 적용될 메소드나 클래스의 범위를 설정하는 것이다.
5. Weaving: Aspect와 핵심 로직을 결합하는 과정을 의미한다.

### AOP 적용 시기
- 로깅 : 메소드 호출 시점, 실행 시간 등을 기록할 때
- 트랜잭션 관리: 데이터베이스 트랜잭션의 시작, 커밋, 롤백을 관리할 때
- 보안 검사: 메소드 호출 전에 사용자 권한을 확인할 때
- 예외 처리: 예외 발생 시 로깅하거나 알림을 보내는 기능이 필요할 때
- 성능 모니터링: 메소드 실행 시간을 측정하거나 서능을 분석할 때

<hr>
<br><br>

## AOP 예시
스프링 프레임워크에서 AOP는 매우 유용하게 사용되며, 스프링 AOP는 주로 <strong>프록시 패턴</strong>을 사용하여 런타임 시에 Advice를 적용한다.
> 트랜잭션 처리를 AOP로 분리하면 비즈니스 로직은 트랜잭션에 대한 코드 없이도 트랜잭션 기능을 사용할 수 있다.
```JAVA
@Aspect
public class LoggingAspect {

    // Pointcut: com.example 패키지 내 모든 메소드에 적용
    @Pointcut("execution(* com.example..*(..))")
    private void logPointcut() {}

    // Advice: 메소드가 실행되기 전에 실행
    @Before("logPointcut()")
    public void logBefore(JoinPoint joinPoint) {
        System.out.println("Executing method: " + joinPoint.getSignature().getName());
    }
}

```
이 예제는 com.example 패키지 내의 모든 메소드가 실행되기 전에 logBefore 메소드가 호출되도록 설정함. 이렇게 하면 각 메소드의 실행 여부를 로깅할 수 있음.

## AOP의 장점
- 중복 코드 제거 : 로깅, 보안, 트랜잭션 관리 등의 코드가 여러 곳에 분산되지 않고, 별도의 모듈로 추상화 됨
- 유지보수성 향상 : 비즈니스 로직과 부가적인 관심사가 분리되므로, 핵심 로직을 수정하지 않고도 횡단 관심사를 쉽게 변경할 수 있음
- 유연성 : 비즈니스 로직은 독립적으로 작성하고, 부가 기능을 쉽게 추가하거나 제거할 수 있어 확장성이 높다.
- 코드 가독성 향상 : 비즈니스 로직 코드에서 부가적인 코드가 제거되므로, 코드가 더 간결해지고 가독성이 높아짐
