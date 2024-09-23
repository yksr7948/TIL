# useContext
## 정의
<code>useContext</code>는 React에서 Context API를 사용하여 컴포넌트 간에 데이터를 쉽게 공유하기 위해 제공되는 Hook이다. 
> 컴포넌트 트리 내에서, 상위 컴포넌트에서 하위 컴포넌트로 데이터를 직접 전달하지 않고도 데이터를 사용할 수 있게 해줌

<hr>
<br><br>

## ⭐ useContext 기본 사용 방법
### 1. Context 생성
```jsx
import React, { createContext, useContext } from 'react';

// 1. Context 생성
const ThemeContext = createContext();
```
먼저 <code>React.createContext()</code>를 사용하여 생성해준다.

### 2. Provider로 값 제공
```jsx
const App = () => {
  return (
    // 2. Provider에서 값을 설정
    <ThemeContext.Provider value="dark">
      <Toolbar />
    </ThemeContext.Provider>
  );
};
```
Provider 컴포넌트를 사용하여 데이터를 제공

### 3. useContext Hook 사용
```jsx
const Toolbar = () => {
  return (
    <div>
      <ThemeButton />
    </div>
  );
};

const ThemeButton = () => {
  // 3. useContext로 값을 사용
  const theme = useContext(ThemeContext);

  return <button style={{ background: theme === 'dark' ? '#333' : '#fff' }}>Theme Button</button>;
};
```
useContext를 통해 제공된 데이터를 사용할 수 있다.
<hr>
<br><br>

## 장점
- 데이터를 필요한 컴포너트에게 바로 전달할 수 있기 때문에 컴포넌트 간에 props로 계속해서 값을 전달할 필요가 없음
- 전역적으로 관리되는 데이터를 쉽게 접근하고 사용할 수 있음

## ❗ 주의사항
- 너무 많은 데이터를 useContext로 관리하게 되면 컴포넌트가 재랜더링되는 경우 성능에 영향을 줄 수도 있음
- useContext로 사용되는 context값이 변경될 떄 해당 context를 구독하는 모든 컴포넌트가 재랜더링이 됨
