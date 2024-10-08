# React 란 무엇인가?

## :page_with_curl: 정의
### React는 사용자 인터페이스를 만들기 위한 JavaScript 라이브러리이다.
> React는 인터렉션이 많은 웹 앱을 개발하기 위해서 주로 사용됨. <br>
> React는 웹 애플리케이션의 복잡한 상태를 효율적으로 관리하고, 대규모 프로젝의 UI의 재사용성과 유지보수성을 높이는데 장점이 있음.
----------
<br>

## :star: React의 주요 개념
### 컴포넌트 기반 아키텍쳐
> React는 컴포넌트라는 재사용 가능한 UI 구성 요소를 기반으로 동작한다. 각 컴포넌트는 독립적이며, 다른 컴포넌트와 결합되어 복잡한 사용자 인터페이스를 구성할 수 있음 <br>
> 예를 들어, 버튼, 입력필드, 전체 화면 자체가 하나의 컴포넌트가 될 수 있음

### JSX (JavaScript XML)
> JSX는 JavaScript에 XML/HTML 구문을 추가한 확장 문법으로, React 컴포넌트를 정의할 때 자주 사용됨. <br>
> JSX를 사용하면 HTML과 유사한 문법으로 UI를 정의할 수 있으며, 이 코드가 JavaScript 코드로 변환되어 브라우저에서 실햄됨.
>
> ![jsxCode](https://github.com/user-attachments/assets/238eb2f7-71bd-4382-9f12-a8d149857306)


### 가상 DOM (Virtual DOM)
> React는 가상 DOM을 사용하여 UI를 업데이트 한다. 가상 DOM은 메모리 내에서 존재하는 가벼운 DOM의 사본 <br>
> React는 UI에서 상태가 변경되었을 때, 먼저 가상 DOM에서 변경 사항을 계산한 후 실제 DOM과 비교하여 차이점만을 업데이트 한다. 이를 통해 성능을 최적화하고, 브라우저의 느린 DOM조작을 최소화함

### 단방향 데이터 흐름
> React는 데이터가 부모 컴포넌트에서 자식 컴포넌트로 전달되며, 자식 컴포넌트는 직접 부모의 상태를 변경할 수 없음

### 상태관리 (State Management)
> React 컴포넌트는 자체적으로 상태를 가질 수 있음. 상태가 변경되면, React는 자동으로 UI를 재랜더링하여 변경 사항을 반영함 <br>
> React의 상태관리가 복잡해질 경우, Redux나 Context API같은 도구를 사용하여 전역 상태를 관리 할 수 있다.

### React Hooks
> 함수형 컴포넌트에서 상태와 라이프사이클 메서드를 사용할 수 있게 해줌. "useState", "useEffect" 같은 훅을 통해 상태 관리, 사이드 이펙트 관리 등을 할 수 있다.
> 
> ![hooksCode](https://github.com/user-attachments/assets/a5ec5b58-6b66-4609-998f-433c14f2c09c)

----------
<br>


## :thumbsup: React의 장점

- 컴포넌트 기반 구조 덕분에 재사용하기 쉽고, 유지보수가 쉽다.
- 가상 DOM을 이용하여 UI 업데이트 성능을 최적화
- 다른 프레임워크나 라이브러리와 혼용하여 사용할 수 있음
- 사용자와 상호작용할 수 있는 동적인 UI를 쉽게 만들 수 있음

## :thumbsdown: React의 단점
- React 생태계는 빠르게 변화하고 새로운 기능이나 도구들이 자주 추가된다.
