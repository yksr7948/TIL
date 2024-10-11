# Spring MVC
Spring MVC패턴은 Spring프레임워크에서 웹 애플리케이션을 개발할 때 사용되는 아키텍쳐 패턴이다. 
MVC는 Model-View-Controller의 약자로 애플리케이션의 비즈니스 로직과 프레젠테이션 로직을 분리하여 구조적으로 더 유연하고 유지보수하기 쉽게 만들어주는 패턴임

## MVC 패턴 구성
### Model
- 애플리케이션의 비즈니스 로직을 처리하고, 데이터를 관리하는 역할
- 데이터베이스와 상호작용하고, 데이터를 가공하거나 처리하여 컨트롤러에게 전달함
- Spring에서는 POJO(Plain Old Java Object) 형태로 데이터를 표현하고, DTO(Data Transfer Object)나 앤티티 클래스들이 모델로 사용됨

### View
- 사용자에게 보여질 UI를 담당하는 부분
- View는 Model로부터 받은 데이터를 화면에 표현함

### Controller
- 사용자의 요청을 처리하고, Model과 View 사이의 흐름을 제어하는 역할을 함
- Spring에서는 @Controller 어노테이션을 사용하여 컨트롤러를 정의한다.
- 사용자의 요청을 받아 해당 요청을 처리할 비즈니스 로직을 호출하고, 그 결과를 View에 전달한다.
- Cotroller는 클라이언트와 상호작용하고 요청에 맞는 데이터를 Model에서 가져오거나 저장하고, 이를 적절한 View에 전달하는 중심 역할이다.

## MVC 패턴 장점
1. 사용자 요청 처리 로직이 각각 Model, View, Controller로 분리되어 유지보수가 용이함
2. 다양한 View 기술을 사용할 수 있고 확장 가능성이 높음
3. DispatcherServlet을 통해 모든 요청을 처리하여 애플리케이션의 흐름을 제어할 수 있음
4. DI, AOP, 보안 등 Sping의 다양한 기능을 사용할 수 있음
