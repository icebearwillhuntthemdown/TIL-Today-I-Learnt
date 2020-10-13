# Control flow 
<br/><br/>
## If
`If`, in Kotlin, is an expression, hence returns a value. Therefore there's no need to use ternary operator as ordinary `if` works just as fine for that role.

```Kotlin
// traditional if statement
var greater: Int
if(a > b) {
    greater = a
}else {
    greater = b
}

// if statement in Kotlin
val greater = if(a > b) a else b    // works as ternary operator


// if block statements 
val max = if(a > b) { 
    print("a is greater than b")
    a       // the last expression is the return value of the block
}else {
    print("b is greater than a")
    b       // the last expression is the return value of the block
}
```
❕ when using `if` as an expression, (1)returning its value, 2)assigning it to a variable) the expression is required to have an `else` branch.

<br/><br/>

## When
`when` replaces `switch` statement in Kotlin but with better 
















