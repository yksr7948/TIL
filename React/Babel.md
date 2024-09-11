# Babel

## 📃 정의
Babel은 최신 JavaScript를 구형 브라우저나 환경에서도 사용할 수 있도록 변환해주는 자바스크립트 컴파일러이다. 

Babel을 사용하면 개발자는 최신 기능을 자유롭게 사용할 수 있으며, 이 코드가 호환되지 않는 환경에서는 Babel이 이를 구버전으로 변환해준다.

<hr>
<br><br>

## ⭐ Babel의 주요 기능
- 코드 변환 : Babel은 ES6 이상의 최신 문법을 구형 문법으로 변환한다. 예를 들어 let이나 const, 화살표 함수 등 ES6 이후 추가된 문법을 구형 브라우저에서도 동작하도록 변환해 준다.
- 플러그인 기반 아키텍쳐 : Babel은 플러그인 기반으로 동작하여, 다양한 플러그인을 성치하여 필요한 기능만 선택적으로 사용할 수 있다.
- JSX 변환 : React에서 사용되는 JSX 구문을 순수 자바스크립트 코드로 변환해준다. JSX는 브라우저가 바로 이해할 수 없는 문법이기 때문에, Babel을 사용하여 변환한다.
- Tree Shaking : Babel은 불필요한 코드나 사용되지 않는 코드를 제거하여 최종 번들 크기를 줄이는 데 도움을 준다.

<hr>
<br><br>

## 🌼 Babel 코드 변환 예시
JSX 코드
```JSX
const element = <h1>Hello, Babel!</h1>;

ReactDOM.render(element, document.getElementById('root'));
```

Babel 변환
```JSX
// Babel로 변환된 코드
const element = React.createElement("h1", null, "Hello, Babel!");

ReactDOM.render(element, document.getElementById('root'));
```

확실히 Babel을 사용하면 코드가 많이 간결해지는 것을 볼 수 있다.
