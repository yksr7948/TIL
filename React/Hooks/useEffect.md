# useEffect
## 정의
<code>useEffect</code>는 React에서 컴포넌의 side Effect를 관리하기 위한 Hook이다. side Effect란 컴포넌트의 랜더링 외에 발생하는 작업으로 데이터 가져오기, DOM 조작, 구독 등이 있다.

<hr>
<br><br>

## ⭐ useEffect의 주요 개념
- 컴포넌트가 랜더링 될 때 실행
  - 컴포넌트가 처음 랜더링 될 때와 이후 업데이트 될 때 <code>useEffect</code> 내부 코드가 실행된다.
- 의존성 배열(Dependency Array)
  - 특정 상태나 props에 변화가 있을 때만 <code>useEffect</code>를 실핼하도록 의존성 배열을 추가할 수 있다.
  - 의존성 배열이 없으면 매번 랜더링 시 실행되고, <Strong>빈 배열([])</Strong>이면 최초 랜더링 시에만 실행 됨  
<br>

### 의존성 배열이 있는 경우
```JSX
useEffect(() => {
  document.title = `You clicked ${count} times`;
}, [count]); // count가 변경될 때만 실행
```
- 첫 번째 매겨변수에는 함수를 입력한다. 이 함수는 컴포넌트가 랜더링 되고 호출된다.
- 렌더링 결과가 실제 돔에 반영되고 비동기로 호출된다. 이 함수를 부수 효과 함수라고 한다.
- 두 번째 매개변수에는 배열을 입력한다. 이 배열을 의존성 배열이라고 부른다.

### 마운트 될 때만 실행하고 싶을 때
```JSX
useEffect(()=> {
    console.log('마운트 될 때만 실행됩니다.')
},[])
```
- 만약 컴포넌트가 화면에 가장 처음 랜더링 될 때만 실행하고 업데이트 할 필요가 없을 때 두 번째 매겨변수에 <Strong>빈 배열([])</Strong> 넣어주면 된다.
- 컴포넌트가 처음 나타날 때만 실행되고 그 이후에는 콘솔에 문구가 나타나지 않는다.

<hr>
<br><br>

## ❗ 컴포넌트 마운트 시 데이터 가져오기
<code>useEffect</code>는 React에서 컴포넌트에서 비동기 작업, DOM 업데이트 등을 처리하는데 사용된다. 특정 조건에서만 실행되도록 제어할 수 있다.

```JSX
import { useState, useEffect } from "react";

function UserProfile({ userId }) {
  const [user, setUser] = useState(null);

  useEffect(() => {
    // 컴포넌트가 마운트될 때 API 호출
    fetch(`https://api.example.com/users/${userId}`)
      .then(response => response.json())
      .then(data => setUser(data));
  }, [userId]); // userId가 바뀔 때마다 실행

  if(!user) {
    return <div>Loading...</div>;
  }else{
    return <div>{user.name}</div>;
  }
}
```
- 이 코드는 userId가 변결될 때마다 데이터를 가져와 상태를 업데이트 한다.
- <code>useEffect</code> 안의 함수는 userId가 변결될 때마다 실행된다.
