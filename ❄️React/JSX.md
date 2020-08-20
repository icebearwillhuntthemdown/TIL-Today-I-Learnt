# JSX
JSX는 JavaScript XML의 약자로, 리액트 요소(elements)를 생성한다. JSX는 HTML을 닮았지만 HTML 요소가 아니라 virtual DOM을 생성한다는 점에서 다르고 또 문법에도 차이가 있다. JSX 표현식은 처리를 거치고 나면 자바스크립트 객체로 취급되기 때문에 자바스크립트 구문 안에 포함될 수 있다.
<br/><br/>

## Why JSX?
프론트 단에는 화면을 만드는 렌더링 로직(rendering logic)과 이벤트 처리, 상태 변화, 데이터 처리 같은 UI 로직이 서로 연결돼 있다. 기존에는 HTML, CSS, JS 파일을 각각 분리함으로써 마크업과 로직을 분리했다. 반면 리액트는 마크업과 로직을 모두 포함하되 느슨하게 결합하는 컴포넌트(components)를 사용한다. 리액트는 애플리케이션을 컴포넌트로 분리하고, 컴포넌트는 state에 변동사항이 발생할 때마다 리렌더링 된다.
<br/><br/>

## Syntax
* { } : embedding JavaScript expressions
  `<h1>Hello, {userName}</h1>`
* Attributes
  * className : HTML의 class 속성에 해당한다. 자바스크립트의 class와 중복되기 때문에 className으로 쓴다.
  * onClick : HTML의 onclick에 해당한다. 자바스크립트의 camel casing 원칙을 따른다.
  
