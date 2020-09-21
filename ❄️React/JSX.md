# JSX
JSX는 JavaScript XML의 약자로, 리액트 요소(elements)를 생성한다. JSX는 HTML을 닮았지만 HTML 요소가 아니라 virtual DOM을 생성한다는 점에서 다르고 또 문법에도 차이가 있다. JSX 표현식은 처리를 거치고 나면 자바스크립트 객체로 취급되기 때문에 자바스크립트 구문 안에 포함될 수 있고 자바스크립트 구문을 포함할 수도 있다.
<br/><br/>

## Why JSX?
프론트 단에는 화면을 만드는 렌더링 로직(rendering logic)과 이벤트 처리, 상태 변화, 데이터 처리 같은 UI 로직이 서로 연결돼 있다. 기존에는 HTML, CSS, JS 파일을 각각 분리함으로써 마크업과 로직을 분리했다. 반면 리액트는 마크업과 로직을 모두 포함하되 느슨하게 결합하는 컴포넌트(components)를 사용한다. 리액트는 애플리케이션을 컴포넌트로 분리하고, 컴포넌트는 state에 변동사항이 발생할 때마다 리렌더링 된다.  

+) 리액트는 1)**state** 또는 2)**props**에 변동이 있어야만 리렌더링 된다. 어떤 변수의 값이 변하더라도 state 또는 props가 변하지 않으면 리렌더링 되지 않으므로 화면상에는 변동사항이 반영되지 않는다.
<br/><br/>

## Syntax
JSX는 HTML을 닮았기 때문에 문법이 유사하다. HTML과 다른 문법만 정리한다.  
* { } : embedding JavaScript expressions  
  `<h1>Hello, {userName}</h1>` `const element = <img src={user.profileUrl}>`
* Attributes
  * className : HTML의 class 속성에 해당한다. 자바스크립트의 class와 중복되기 때문에 className으로 쓴다.
  * onClick : HTML의 onclick에 해당한다. 자바스크립트의 camel casing 원칙을 따른다.
  * key : 요소를 구분하기 위한 식별자.  
    You need a key attribute to differentiate the each element from others so that React can only **react** to those that are actually changed
    * Anytime you use the map() inside of render
    * Anytime you have a list of jsx elements one after another
* style  
  * inline : `<div style={{height: '100px', backgroundColor: 'blue'}}></div>`
  * CSS : `<div className="myCss"></div>`
<br/><br/>

## JSX Represents Objects
Babel이 `React.createElement()`를 호출해 JSX를 컴파일하면 자바스크립트 객체가 된다. 이 객체들을 리액트 요소(React elements)라고 부르고 리액트는 이 객체들을 통해 DOM을 생성하고 조작한다. 리액트 함수는 하나의 JSX 객체만을 리턴한다.
```javascript
//JSX syntax
const element = (
  <h1 className = "greeting">
    Hello, world!
  </h1>
);

//Babel이 컴파일
const element = React.createElement(
  'h1',
  {className : 'greeting'},
  'Hello, world!'
);

//컴파일 결과 자바스크립트 객체화
const element = {
  type: 'h1',
  props: {
    className: 'greeting',
    children: 'Hello, world!'
  }
};
```


