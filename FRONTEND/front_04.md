## React 

## CSS 
`.jsx` 파일에서 `className`으로 지정한 스타일 속성은 `.css` 파일에서 class 선택자를 통해 정의함

__`.`__: 태그의 `className` 속성에 지정된 이름을 스타일링할 때 사용함 (ex: `.login-container`)  

__`.`이 없는 경우__ (ex: `div`, `input`, `button`...): HTML의 태그 이름 자체를 선택하여, 해당 타입의 모든 태그에 공통으로 스타일을 적용

---

## Axios 
프론트엔드와 백엔드 간의 HTTP 요청/응답을 효율적으로 처리하기 위한 라이브러리

__설치__

```bash
npm install axios
```
- __CRUD 기능 지원__: axios.get(), axios.post(), axios.put(), axios.delete() 등을 통해 데이터 통신 수행

- __비동기 처리 지원__: 기본적으로 비동기 방식으로 동작하지만, async / await 문법을 활용하여 서버의 응답이 돌아올 때까지 기다리도록 작성 가능

__Login.jsx__
```jsx
import axios from "axios";

// 로그인 API 요청
const response = await axios.post("http://localhost:8080/api/login", {
    // 화면에 입력한 id, password 파라미터를 json 형식으로 저장
    username: userId,
    password: password,
});

// 응답으로 받은 토큰 저장
const token = response.data.token;
localStorage.setItem('token', token);

// 로그인 성공
alert('로그인 성공!');
setError('');
```
---

## react-router-dom
__설치__

```bash
npm install axios
```

__App.js__
```js
// router-dom 사용을 위한 import
import { BrowserRouter as Router, Routes, Route } from "react-router-dom";

// <Route>가 하나의 컴포넌트를 의미

function App() {
  return (
    <Router>
      <Routes>
        <Route>
        </Route>
      </Routes>
    </Router>
  );
}
