# State란?

## 📃 정의
React에서의 State는 상태를 뜻한다. 다시 말해 State는 컴포넌트 내에서 지속적으로 변경이 일어나는 값을 관리하기 위해 사용한다.
개발자가 의도한 동작에 의해 변할 수도 있고 사용자의 입력에 따라 새로운 값으로 변경될 수도 있다.

State 값이 변경되고 재 랜더링이 필요한 경우에 React가 자동으로 계산하여 변경된 부분을 랜더링 한다.

<hr>
<br><br>

## ⭐ State 사용법
```JavaScript
import { useState } from "react";
 
const App = () => {
    const [value, setValue] = useState(초기값);
    return ...
}
```
- State 값을 변경하기 위해서는 반드시 setState 함수를 사용해야 한다.
- State 값을 임의로 변경해선 안 된다.

<br><br>

### 🔥 잘못된 방법
```JavaScript
import { useState } from 'react';
 
function Example() {
    const [count, setCount] = useState(0);
    return (
        <div>
            <p>버튼을 {count}번 눌렀습니다.</p>
            <button onClick={() => {count = count + 1;}>클릭</button> // 이렇게 하면 안 된다.
        </div>
    );
}
```
- State 값을 직접 변경하게 되면 React가 Component를 다시 랜더링 할 타이밍을 알아차리지 못한다.

### 🌼 올바른 방법
```JavaScript
import React, { useState } from "react";

function App() {
  const [count, setCount] = useState(0);

  const handleClick = () => {
    setCount(count + 1);
  };

  return(
    <>
      <button onClick={handleClick}>버튼</button>
      <p>버튼을 {count}번 눌렀습니다.</p>
    </>
  );
}

export default App;

```
- setState 함수를 호출을 하면 React에게 랜더링을 하라는 명령을 내린다. 
