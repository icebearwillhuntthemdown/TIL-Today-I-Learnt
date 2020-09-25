# State and Props

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
