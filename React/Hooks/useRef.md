# useRef
## 정의
useRef는 React에서 제공하는 Hook으로, 컴포넌트 내에서 DOM 요소나 값을 참조할 수 있는 방법을 제공한다. 

1. DOM 요소에 접근 : useRef는 특정 DOM 요소에 직접 접근할 수 있는 방법을 제공한다. 예를 들어, 폼 입력 필드에 focus를 주거나, 스크롤 위치를 제어하는 작업에서 유용하다.
2. 리랜더링 없음 : useState와 달리 useRef를 통해 저장된 값이 변경되더라도 컴포넌트는 다시 랜더링 되지 않는다. (컴포넌트가 자주 랜더링되는 상황에서 좋음)

<hr>
<br><br>

## 사용방법
```JS
import React, { useRef } from 'react';

function TextInputWithFocusButton() {
  // useRef를 사용하여 input 요소를 참조
  const inputEl = useRef(null);

  const onButtonClick = () => {
    // current 프로퍼티를 통해 input 요소에 접근
    inputEl.current.focus();
  };

  return (
    <>
      <input ref={inputEl} type="text" />
      <button onClick={onButtonClick}>Input에 포커스 주기</button>
    </>
  );
}
```
- <code>input ref={inputEl}</code>를 통해 input 요소를 inputEl에 연결
- 버튼을 클릭하면 inputEl.current를 통해 input 요소에 접근하고, focus() 메서드를 호출해 포커스를 줌

## 주요 특징
- 리랜더링 되지 않음
- .current 프로퍼티를 가지며, 컴포넌트의 라이프사이클 동안 유지된다.
