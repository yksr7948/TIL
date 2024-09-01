# JSX란?

## 정의
JSX는(JavaScript eXtension)는 JavaScript를 확장한 문법이다. 자바스크립트에서 HTML을 작성하듯이 하기 때문에 가독성이 좋고 작성하기 쉽다.
- 리액트로 프로젝트를 개발할 때 사용되므로 공식적인 자바스크립트 문법은 아니다.
- 브라우저에서 실행하기 전에 바벨을 사용하여 일반 자바스크립트 형태의 코드로 변환된다.

#### ex).
```JavaScript
// 실제 작성할 JSX 예시
function App() {
	return (
      <h1>Hello, Everyone!</h1>
    );
}

// 위와 같이 작성하면, 바벨이 다음과 같이 자바스크립트로 해석하여 준다.
function App() {
	return React.createElement("h1", null, "Hello, Everyone!");
}
```

<br>

## JSX 문법
- 컴포넌트에 여러 요소가 있다면 부모 요소 하나로 감싸는 형태로 만들어야 한다.
```JavaScript
function App(){
    return(
      <>
        <h1>테스트1</h1>
        <h2>테스트2</h2>
      </>
    )
}
```

이처럼 바깥을 React.Fragment로 감싼 형태로 작성해야한다.

이렇게 감사는 이유는, 리액트가 사용하는 Virtual DOM 방식에서는 컴포넌트 변화를 감지할 때 효율적으로 비교하고자 컴포넌트 내부는 하나의 DOM 트리 구조로 이루어져야 한다는 규칙이 있기 때문이다. 

<br><br>

- 자바스크립트 값을 JSX 안에서 랜더링 할 수 있다.
```JavaScript
import React from 'react';

function App() {
	const name = '리액트';
    return (
    <>
    	<h1>{name}</h1>
        <h2>test</h2>
    </>
  );
}

export default App;
```
이처럼 name의 값을 {} 중괄호 안에 넣어 자바스크립트 값을 표현할 수 있다.

<br><br>

- JSX 내부의 자바스크립트 표현식에서는 if문을 사용할 수 없으니 삼항 연산자를 사용한다.
```JavaScript
function App() {
    const name = '치킨';
  return (
   <div>
          {name === '치킨'? (
          	<h1>치킨</h1>
          ) : (
          	<h2>피자</h2>
          )}
      
   </div>
      
  );
}
export default App;
```

<br><br>

- JSX 상에서는 무조건 {} 오브젝트로 바꿔서 넣어야 한다.

HTML
```html
<div style="font-size : 16px">글씨</div>
```

JSX
```JavaScript
<div style={{fontSize : '16px'}}> 글씨 </div>
```
- {속성명 : '속성값'}
- font-size => fontSize

<br><br>

- HTML에서 class를 주고싶으면 class를 사용하면 되지만 JSX에서는 className을 사용해야 한다.
HTML
```html
<div class="className">
    
</div>
```

JSX
```JavaScript
<div className="className">
    
</div>
```

<br><br>

- HTML에서는 input 태그 등 태그를 닫지 않아도 되지만, JSX에서는 반드시 닫아주는 태그를 작성해야 한다.
```JavaScript
<input></input>
// 혹은 다음과 같이 self-closing 태그로 작성해도 무방
<input />
```

<hr>
