## React

사용자 인터페이스를 만들기 위한 __자바스크립트 라이브러리__

- __Component-Based__: 부품 단위로 쪼개서 개발함
- __Library vs Framework__
  - __Library__: 개발자가 필요할 때 직접 라이브러리를 호출해서 주도적으로 사용함 (React)
  - __Framework__: 프레임워크가 정의한 틀과 규칙 안에서 개발자가 코드를 맞춰 작성하면, 프레임워크가 스스로 구동함

---

## Component와 Element

## Component
- 화면에 보여질 element를 생성하는 틀
- __JavaScript Function__ 형태로 정의하며, 파일 확장자는 주로 __`.jsx`__ 를 사용함 (`xxx.jsx`)
- 일반 함수가 입력값을 받아 출력값을 내는 것처럼, 컴포넌트는 `props`를 받아 `element`를 생성하고 최종적으로 브라우저 화면에 렌더링함
  - 일반 함수: __입력 -> 출력__
  - 컴포넌트: __props -> element__

## Element
- 리액트 앱을 구성하는 __가장 작은 단위__
- 화면에 최종적으로 보여지는 구조를 기술하는 것
- 각 엘리먼트들은 서로 다른 속성(Property) 값을 가질 수 있음

## Props
- 컴포넌트에 전달되는 속성들의 집합 (__Properties__)

---

## SPA(Single Page Application)
리액트는 __SPA(Single Page Application)__ 아키텍처를 기반으로 동작함

- __기존 웹사이트__: 새로운 페이지로 이동할 때마다 서버로부터 전체 HTML 파일을 매번 새로 다운로드
- __SPA__ : 처음에 __하나의 HTML 파일__ 만 서버로부터 다운로드받은 뒤, 사용자가 클릭하는 메뉴나 동작에 따라  필요한 컴포넌트 부분만 실시간으로 업데이트함 

