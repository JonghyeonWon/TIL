
## React

- __node.js__ + __npm(node package manager)__ 기반
- __git bash__에서 `node -v`, `npm -v` 명령어로 각각 버전 확인 가능

---

__CRA 프로젝트 생성__
```bash
npx create-react-app [project 이름]
# ex) npx create-react-app react_pjt 
```

__서버 실행__
```bash
npm start
```

---

__tag__ 에 자주 이용되는 속성
- __class__: __CSS__ 에서 접근할 때 사용
- __id__: __script__ 에서 접근할 때 사용


__src/index.js__

- `index.html`에서 id가 root인 element를 찾아 그 위치에 가상의 돔을 만듦

```javascript
const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(
  <React.StrictMode>
    <App />
  </React.StrictMode>
);

```

__public/index.html__
- 하나의 유일한 html 파일
- 이 파일 내부에 존재하는 `<div id="root"></div>` 공간에 리액트 컴포넌트들이 주입됨

__src/App.js__

- function을 기반으로 App이라는 컴포넌트가 정의됨

```javascript
function App() {
  return (
    <div className="App">
      <header className="App-header">
        <img src={logo} className="App-logo" alt="logo" />
        <p>
          Edit <code>src/App.js</code> and save to reload.
        </p>
        <a
          className="App-link"
          href="[https://reactjs.org](https://reactjs.org)"
          target="_blank"
          rel="noopener noreferrer"
        >
          Learn React
        </a>
      </header>
    </div>
  );
}

// 만들어진 컴포넌트를 외부에서 사용할 수 있도록 export
export default App;

```
