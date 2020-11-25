# Returns and Jumps
* return : returns from the nearest function or anonymous function
* break : terminates the nearest enclosing loop
* continue : proceeds to the next step of the nearest enclosing loop
```Kotlin
val s = person.name ?: returns
```

+) `Nothing` type
- `Nothing` type has no values
- you can use `Nothing` to make a function that never returns
- `return`, `break`, `continue` has type `Nothing`
- `throw` exception has type `Nothing`
```Kotlin
fun throwException(msg: String): Nothing {
    throw IllegalArgumentException(msg)
}
```

# Returns and Jumps With Label
## Label
- Any expression in Kotlin can be labelled
- Syntax: `label@` followed by an expression
- Calling: `@label` following return, break, and continue

## Break and Continue with Label
- `break` with a label jumps out of the labelled loop
- `continue` with a label skipps to the next iteration of the loop
```Kotlin
loop@ for(being in beings) {
    for(dog in happyDoggies) {
        if(being.equals(dog)) break@loop
    }
}
```

## Return with Label
`return` with label can function like both `break` and `continue`, depending on the context.

1. **return from a lambda**
works like `break`
```Kotlin
fun foo() {
    listOf(1, 2, 3, 4, 5).forEach {
        if (it === 3) return    // returns from foo(), the nearest function
        print(it)               // prints 1, 2
    }
    println("This can't be printed")
}
// output: 12
```

2. **return from a lambda with expicit label**
works like `continue`
```Kotlin
fun foo() {
    listOf(1, 2, 3, 4, 5).forEach @here{
        if (it === 3) return@here   // return from labelled expression, forEach
        print(it)                   // prints 1, 2, 4, 5 
    }
    print("done with explicit label!")
}
// output: 1245 done with explicit label!
```

3. **return from a lambda with implcit label**
works like `continue`
```Kotlin
fun foo() {
    listOf(1, 2, 3, 4, 5).forEach {
        if (it === 3) return@forEach    // return from forEach
        print(it)                       // prints 1, 2, 4, 5
    }
    print("done with implicit label!")
}
// output: 1245 done with implicit label!
```

4. **return from an anonymous function**
works like `continue`, an alternative to lambda 
```Kotlin
fun foo() {
    listOf(1, 2, 3, 4, 5).forEach(fun(value: Int) {
        if (value === 3) return     // return from the anonymous function
        print(value)                // 1, 2, 4, 5
        })
    print("done with anonymous function!")
}
// output: 1245 done with anonymous function!
```

5. **return from another nesting lambda**
works like `break`
```Kotlin
fun foo() {
    run here@{
        listOf(1, 2, 3, 4, 5).forEach {
            if (it === 3) return@here   // return from run {}
            print(it)                   // prints 1, 2
        }
    }
    print("done with nested lambda")
}
// output: 12 donw with nested lambda 
```

+) `run {}`
`inline fun <R> run(block: () -> R): R`
calls the specified function block and returns its value
**to be added later**


## References
- https://kotlinlang.org/docs/reference/returns.html
