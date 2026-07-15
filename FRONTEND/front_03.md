## React 

## JSX
자바스크립트 확장 문법으로, __JavaScript__ 안에서 __HTML__을 직접 작성할 수 있는 파일(`.jsx`)

- __className__: 자바스크립트의 예약어인 `class`와의 충돌을 피하기 위해, 리액트에서는 CSS를 적용할 때 __`className`__ 속성을 사용함

---

## Login 컴포넌트 구현

__src/component/page/Login.jsx__

```jsx
import React, { useState } from 'react';
import '../css/Login.css';

// function 이름은 file 이름과 동일해야함
const Login = () => {

    // 상태 관리를 위한 hook 정의
    const [userId, setUserId] = useState("");
    const [password, setPassword] = useState("");
    const [error, setError] = useState("");

    // handler 정의
    const handleSubmit = (e) => {

        e.preventDefault();
        console.log('btn click event');
    }

    // html 작성
    return (
        // react에서는 css를 적용할 때 예약어의 역할을 하는 class 대신 className 사용
        // 버튼이 눌렸을 때 handleSubmit라는 handler 호출
        <div className = "login-container">
            <form className = "login-box" onSubmit = {handleSubmit}>
                <h2>로그인</h2>

                <div className = "input-group"> 
                <label>아이디</label>
                <input 
                    type = "text"
                    placeholder = "아이디를 입력하세요"
                    value = {userId}
                    // 상태 관리 함수 호출
                    onChange = {(e) => setUserId(e.target.value)}
                />
                </div>

                <div className = "input-group"> 
                <label>비밀번호</label>
                <input 
                    type = "password"
                    placeholder = "비밀번호를 입력하세요"
                    value = {password}
                    // 상태 관리 함수 호출
                    onChange = {(e) => setPassword(e.target.value)}
                />
                </div>

                {error && <p className = "error-message">{error}</p>}

                <button type = "submit" className = "login-btn">
                    로그인
                </button>
            </form>
        </div>
    );
}

// 외부에서 사용 가능하도록 export
export default Login;
```

---

## Login 컴포넌트 삽입
__src/component/page/Login.jsx__

```jsx
// 새로 정의한 Login 컴포넌트 삽입
import Login from './component/page/Login';

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(
  <React.StrictMode>
    <Login />
  </React.StrictMode>
);
```

