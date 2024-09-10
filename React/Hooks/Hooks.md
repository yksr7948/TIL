# Hooks
## 📃 정의
Hooks는 함수형 컴포넌트에서 상태 관리와 생명 주기(Life Cycle) 기능을 사용할 수 있도록 도와주는 기능이다. 

이전에는 클래스형 컴포넌트에서만 상태나 라이프사이클 매서드를 사용할 수 있었지만, React Hooks를 통해 함수형 컴포넌트에서도 동일한 기능을 구현할 수 있게 되었다.

<hr>
<br><br>

## ⭐ React Hooks의 주요 종류
### 1. useState
  - 상태 변수를 선언하고 이를 변경하는 함수를 제공하는 Hook
    
```JavaScript
const [count, setCount] = useState(0);
```
### 2. useEffect
  - 컴포넌트가 랜더링 되거나 상태가 변경될 때 틀정 작업을 실행할 수 있도록 도와주는 Hook
    
```JavaScript
 useEffect(() => {
  document.title = `You clicked ${count} times`;
}, [count]);
```
### 3. useContext
  - Context API를 활용해, 컴포넌트 간에 데이터를 전역적으로 공유할 때 사용하는 Hook
  - 부모 컴포넌트로부터 자식 컴포넌트로 prop을 여러 단계에 걸쳐 전달할 필요 없이 데이터를 전달 할 수 있다.

```JavaScript
const value = useContext(MyContext);
```
### 4. useReducer
  - 복작한 상태 관리를 위해 <code>useState</code> 대신에 사용할 수 있는 Hook으로, 상태와 상태를 변경하는 로직을 분리하여 코드의 복잡도를 낮추는 Hook
```JavaScript
const [state, dispatch] = useReducer(reducer, initialState);
```
### 5. useMemo
  - 계산 비용이 큰 작업의 결과를 메모이제이션하여 성능 최적화를 하는 Hook
```JavaScript
const memoizedValue = useMemo(() => computeExpensiveValue(a, b), [a, b]);
```
### 6. useCallback
  - 함수의 재생성을 방지하여 불필요한 랜더링을 피하는 Hook
  - 의존성 배열의 값이 변하지 않으면 동일한 함수 객체를 반환
```JavaScript
const memoizedCallback = useCallback(() => {
  doSomething(a, b);
}, [a, b]);
```
### 7. useRef
  - DOM 요소나 자식 컴포넌트에 접근할 수 있도록 하는 Hook으로, 변화가 발생해도 컴포넌트를 다시 랜더링 하지 않도록 하는 Hook
```JavaScript
const inputEl = useRef(null);
```

<hr>
<br><br>

## 👍 장점
- 클래스형 컴포넌트보다 훨씬 간단한 함수형 컴포넌트를 통해 상태 관리와 사이드 이펙트 처리를 할 수 있다.
- 여러 컴포넌트에서 공통 기능을 쉽게 재사용할 수 있다.
- 코드의 가독성이 좋아진다.

## 👎 단점
- <code>useEffect</code>와 같은 Hook을 남발하면 코드가 오히려 복잡해진다.
