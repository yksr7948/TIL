# Axios
## 📃 정의
Axios는 브라우저와 Node.js 환경에서 사용되는 <b>Promise 기반의 HTTP 클라이언트</b>로, 주로 비동기적인 HTTP 요청을 간편하게 처리하기 위해 사용된다.

API 호출을 통해 서버와 데이터를 주고 받을 때 많이 쓰이며, JSON 형식의 데이터를 주고받는다.

## ⭐ Axios 사용법
Axios 다운로드
```cmd
npm install axios
```
Axios 기본 사용법
```JavaScript
// ES6 방식
import axios from 'axios';

axios.get('https:/????')
.then(response => {
  console.log(response.data);  // 서버로부터 받은 데이터를 출력
})
.catch(error => {
  console.error('Error fetching data:', error);  // 오류 처리
});
```


## ⭐ 주요 기능
### 1. GET, POST, PUT, DELETE 요청
```JavaScript
// GET 요청 예시
axios.get('/api/movies')
  .then(response => console.log(response.data))
  .catch(error => console.error(error));

// POST 요청 예시
axios.post('/api/movies', { title: 'Inception', year: 2010 })
  .then(response => console.log(response.data))
  .catch(error => console.error(error));
```
서버와의 HTTP 통신에서 기본적인 GET, POST, PUT, DELETE 요청을 보낼수 있다.

### 2. Promise 및 async/await
```JavaScript
// async/await 예시
async function fetchData() {
  try {
    const response = await axios.get('/api/movies');
    console.log(response.data);
  } catch (error) {
    console.error(error);
  }
}
```
Axios는 Promise 기반이므로 비동기 작업에 then, catch 체인을 사용할 수 있고, async/await 패턴으로도 사용할 수 있다.
> async/await 패턴이란?
> - async 함수는 항상 Promise를 반환한다. 함수 내에서 비동기 처리를 할 수 있게 만들어줌
> - await는 Promise가 해결될 때까지 기다리는 역할을 한다. await는 Promise가 완료될 때까지 코드를 멈추게 한 다음, 결과 값을 반환한다.
> - try/catch 구문을 사용하여 에러를 처리할 수 있음.

## Axios의 장점
- then, catch, async/await 등의 비동기 패턴을 사용하여 코드 작성이 직관적이고 간결해진다.
- 브라우저와 Node.js 환경에서 사용 가능
- 요청과 응답을 중간에 처리할 수 있어 효율적인 작업 처리가 가능
- 불필요한 요청을 취소할 수 있는 기능으로 리소스를 절약

## Axios 사용이 적합한 경우
- 클라이언트-서버 간 데이터 통신에서 비동기적으로 데이터를 주고받는 작업이 많은 경우.
- 다양한 HTTP 요청을 수행하며, 데이터 처리 및 에러 처리가 중요한 경우.
- API 호출 전/후에 특정 로직을 처리해야 하는 경우 (인터셉터 활용).
