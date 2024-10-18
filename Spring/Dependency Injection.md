# DI (Dependency Injection, 의존성 주입)
DI은 객체지향프로그래밍에서 객체 간의 의존 관계를 외부에서 주입하는 설계 패턴이다. 즉, 의존성을 클래스 내부에서 생성하거나 결정하지 않고, 외부에서 주입받아 사용하는 방식이다.

<br>

## DI 목적
DI의 목적은 객체간의 **`결합도`**를 낮추는 것이다. 

객체는 자신이 사용할 다른 객체의 생성 및 생명주기를 관리하지 않고, 외부에서 제공받음으로써 유연하고 테스트하기 쉬운 코드를 작성할 수 있음

<br>

## DI의 장점
1. 유연한 설계 : 객체가 다른 객체에 대해 구체적인 구현에 의존하지 않고, 인터페이스나 추상클래스에 의존하게 되어 유연한 설계를 할 수 있음
2. 결합도 감소 : 객체 간의 결합도가 낮아지므로, 특정 객체를 다른 구현체로 구현하거나, 유닛 테스트에서 mock 객체를 주입하여 테스트할 수 있음
3. 코드 재사용성 증가 : 의존성이 명시적으로 주입되기 떄문에, 객체 간의 관계가 명확해지고, 여러 곳에서 동일한 의존성을 재사용할 수 있음
4. 테스트 용이성 : DI는 의존하는 객체들을 쉽게 mock이나 stub으로 대체할 수 있게 하여, 단위 테스트 작성이 더 쉬워짐


<hr>
<br><br>

## Spring F/W 에서 DI
Spring은 컨테이너가 객체의 의존성을 관리하며, Bean으로 동록된 객체 간의 의존성을 주입한다.

### 스프링에서 DI 설정
1. 어노테이션 기반 DI
   - 주로 @Autowired, @Inject, @Resource 같은 어노테이션을 사용하여 자동으로 의존성을 주입한다.
```java
@Service
public class UserService {
    @Autowired
    private UserRepository userRepository;

    public void registerUser(User user) {
        userRepository.save(user);
    }
}

```
2. 자바 설정 클래스를 사용한 DI
   - 자바 설정 파일에서 Bean을 정의하고, @Bean 어노테이션을 통해 의존성을 주입한다.
```java
@Configuration
public class AppConfig {
    
    @Bean
    public UserService userService() {
        return new UserService(userRepository());
    }

    @Bean
    public UserRepository userRepository() {
        return new UserRepositoryImpl();
    }
}
```
3. XML 설정 파일을 통한 DI
```java
<bean id="userService" class="com.example.UserService">
    <property name="userRepository" ref="userRepository" />
</bean>

<bean id="userRepository" class="com.example.UserRepositoryImpl" />

```
