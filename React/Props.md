# Props란?
## :page_with_curl: 정의
Props(property)는 상위 컴포넌트가 하위 컴포넌트에게 값을 전달할 때 사용하는 속성이다. 

## :mega: 특징
- 상위 컴포넌트가 하위 컴포넌트에게 값을 전달하기 때문에 단방향 데이터 흐름을 갖는다.
- 부모 컴포넌트는 수정 가능하지만, 하위 컴포넌트는 수정이 불가능 하다. (읽기만 가능)

<hr>
<br><br>

## :star: props의 기본 사용법
- props에 문자열을 전달할 때는 ""를, 문자열 외의 값을 전달할 때는 {} 을 사용한다.

<hr><br>

App.js
```JavaScript
import React from "react";
import MyComponent from "./MyComponent";

function App() {
    return(
      <MyComponent propValue="안녕하세요"> 김태웅이에요!!</MyComponent>
    );
}

export default App;
```

MyComponent.js
```JavaScript
import React from 'react'

function MyComponent(props) {
  return (
    <div>
      {props.propValue}, {props.children}
    </div>
  )
}

export default MyComponent
```

결과 화면

![image](https://github.com/user-attachments/assets/8c8307f8-2a04-44fe-ab55-3d80b238e672)

MyComponents 컴포넌트에서 상위 컴포넌트로 부터 받은 Props 데이터를 뷰에 랜더링 해준다.
- <strong> {props.propValue} </strong> : 상위 컴포넌트에서 propsValue라고 정의했기 때문에 {props.propValue} 로 나타낸다.
- <strong> {props.children} </strong> : 컴포넌트 태그 사이에 내용을 보여주는 props의 속성

<hr>
<br><br>

## :blossom: 구조분해할당 (Destructuring)
구조분해를 사용하면 더 보기 쉽게 props에 접근할 수 있다.

<strong> 구조분해란? 객체 안에 있는 필드 값을 원하는 변수에 대입할 수 있는 기능이다. 코드의 가독성을 높이고 간략화를 할 때 유용하게 사용된다. </strong>

```JavaScript
import React from "react";

// MyComponent.js
function MyComponent({ propValue, children }) { 
    return (
        <div>
            <p>{propValue}</p>
            <p>{children}</p>
        </div>
    );
}

export default MyComponent;
```
