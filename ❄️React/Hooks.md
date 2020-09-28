# Hooks

A hook is a special function that lets you "hook into" React features. `useState` is a Hook tat lets you add React state to function components. Thanks to hooks we can write a function component with state, without having to convert it to a class component.

## `useState`
### Syntax
`const [currentState,setStateFunction] = useState(initialState);`

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

## `useEffect`
`uesEffect` hook allows you to tell React that your component needs to do somthing after every render. It works like the combination of `componentDidMount`, `componentDidUpdate`, and `componentWillUnmount`.

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


## Other hooks
There are other built-in Hooks APIs explained [here](https://reactjs.org/docs/hooks-reference.html)
