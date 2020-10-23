# Hooks

A hook is a special function that lets you "hook into" React features. `useState` is a Hook tat lets you add React state to function components. Thanks to hooks we can write a function component with state, without having to convert it to a class component.
<br/><br/>

## `useState`
### Syntax
`const [currentState,setStateFunction] = useState(initialState);`

+) 배열의 state  
```Typescript
const [wbb, setWbb] = useState<Bears[]>([])
setState(['Icebear', 'Grizz', 'Panda'])
```

+) 꼭 값이 변하는 동적인 변수에만 state를 쓴다고 생각했는데 아니었다. async API의 response를 state에 담기도 한다. 리액트는 state 또는 props가 변해야만 re-render 되므로 처음 렌더링 됐을 때는 값이 비어있다가 setState로 값을 할당하면 다시 렌더 돼 화면에 나타난다.

### Example
```Typescript
function AFunctionComponent() {
    // Declaring a state variable
    const [count, setCount] = useState(0)
}

// Updating state
<button onClick = {() => setCount(count + 1)}>
    Click me
</button>

// Reading state
<p>You clicked {count} times/p>
```
<br/><br/>

## `useEffect`
`uesEffect` hook allows you to tell React that your component needs to do somthing **after every render**. It works like the combination of `componentDidMount`, `componentDidUpdate`, and `componentWillUnmount`.

### Syntax
```Typescript
useEffect(() => {
    // some effect function
})
```

### Example
```Typescript
function AFunctionComponent() {
    const [count, setCount] = useState(0)

    // pass the effect function to the useEffect Hook
    useEffect(() => {
        document.title = `You've clicked ${count} times`
    })
}
```

### Conditional
To avoid effect overkill, you can specify a certain `source` to bind with an effect by passing it as the second argument to `useEffect`.
```Typescript
useEffect( () => {
    const subscription = props.source.subscribe()
    return () => {
        subscription.unsubscribe()
    }
}, [props.source])
```
<br/><br/>

## Other hooks
There are other built-in Hooks APIs explained [here](https://reactjs.org/docs/hooks-reference.html)
