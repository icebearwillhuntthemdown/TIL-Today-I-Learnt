# Component, State, and Props

## Component
Components are like JS **functions** for accepting arbitrary inputs(props) and return React elements describing what should appear on the screen.  

A component can be either 1)class, or 2)function, but the same rules are applied in both cases   
1. the name starts with a capital letter in both cases  
2. returns a React element(jsx)  

### Class component
```Javascript
class someComponent extends React.component{

```
<br/><br/>

### functional component
functional components don't have access to state and lifecycle methods.(as they are part of a class). functional components are only for render() purpose, so it takes props and returns jsx.

+) break down components : the smaller, more reusable. break down components so that they only implement one small thing.
<br/><br/>

## props & state
- props
    - JSX attributes and children as a single object
    - read-only : all React components must act like pure functions that doesn't chage their inputs

- state : **private** and encapsulated, fully controlled by the component
    + do not modify state directly : use setState()
    + `this.state` is only put in the constructor 
    + state trickles down and gets turned into props of other components

```Javascript
function _component(props){
    return <h1>Hello, {props.name}</h1>
}

class _Component extends React.Component{
    render(){
        return <h1>Hello, {this.props.name}</h1>
    }
}

```

## events
- Synthetic event : 
- no ()s in event handlers : event
```Javascript
render(){
    // 버튼을 클릭하지 않아도 redner()를 부르면 실행되므로 onClick = 리턴값 
    <button onClick = {this.handleClick()}> click </button> 
    // onClick = 함수를 가리키므로 버튼을  실행됨    
    <button onClick = {this.handleClick}> click </button>
}

```


## Lifecycle methods
- constructor()
- render()
- componentDidMount() : runs after the component output has been rendered to the DOM
- componentDidUpdate()
- componentWillUnmount() : runs after the created DOM is removed.
