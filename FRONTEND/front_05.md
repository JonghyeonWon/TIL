## React 

## react-router-dom 

__라우팅 체계 구축__
`BrowserRouter`, `Routes`, `Route`, `useNavigate`를 활용하여 URL 경로에 따른 컴포넌트 매핑

__App.js__
```jsx
// router-dom 사용을 위한 import
import { BrowserRouter as Router, Routes, Route } from "react-router-dom";

import Login from './component/page/Login';
import Welcome from './component/page/Welcome';

// <Route>가 하나의 컴포넌트를 의미
function App() {
  return (
    <Router>
      <Routes>
        // path 이름 정의
        <Route path = '/' element = {<Login>

        </Login>}>
        </Route>

        <Route path = '/welcome' element = {<Welcome>
          
        </Welcome>}>
        </Route>

      </Routes>
    </Router>
  );
}

export default App;
```
`Route`에서 정의한 path 이름을 통해 원하는 페이지로 쉽게 이동이 가능  

__Login.jsx__
```jsx
// 성공 이후 path 이름을 통해 welcome 페이지로 navigate
// state를 이용해 상태 정보 전달
moveUrl('/welcome', { state : { username : userId} });
```
---

__Welcome.jsx__
```jsx
import { useNavigate, useLocation } from 'react-router-dom';

const Welcome = () => {

    // 필요한 훅 정의
    const moveUrl = useNavigate();
    const location = useLocation();

    // Login.jsx에서 state에 저장한 값을 불러옴
    const username = location.state?.username || 'Guest';

    // handleLogout 핸들러 정의
    const handleLogout = () => {
        moveUrl('/');
    }

    return (
        <div style = {styles.container}>

            <h1>
                환영합니다, {username}님!
            </h1>

            <p> 
                로그인이 성공적으로 완료되었습니다.
            </p>

            <button onClick = {handleLogout} style = {styles.btn}>
                로그아웃
            </button>

        </div>
    );
}
```
---
## 인라인 스타일시트 
- 태그 내부에 객체 형태로 스타일을 직접 주입하는 방식

__Welcome.jsx__
```jsx
// styles 변수 정의
const styles = {
    container: {
        marginTop: "100px",
        textAlign: "center",
        fontFamily: "Noto Sans KR, sans-serif",
    },
    btn: {
        marginTop: "20px",
        padding: "10px 20px",
        background: "#0984e3",
        color: "#fff",
        border: "none",
        borderRadius: "8px",
        cursor: "pointer",
    },
}

// 정의한 스타일 변수 이용
<div style = {styles.container}>
<button onClick = {handleLogout} style = {styles.btn}>
```