# Higher-Order Functions & Lambda

## Higher-Order Functions
Functions that takes other functions as paramters or returns one. 

### Example: fold
JS의 reduce와 같다.
```Kotlin
val items = listOf(1, 2, 3, 4, 5)

// Lambdas are code blocks enclosed in curly braces.
items.fold(0, {
    // When a lambda has parameters, they go first, followed by '->'
    acc: Int, i: Int ->             
    print("acc = $acc, i = $i, ")
    val result = acc + i
    println("result = $result")

    // The last expression in a lambda is considered the return value
    result
})

// Parameter types in a lambda are optional if they can be inferred
val joinedToString = items.fold("Elements: ", { acc, i -> acc + " " + i })  // both are inferred as Strings

// Function references can also be used for higher-order function calls
val product = items.fold(1, Int::times)     
```

# Lambda
[DSL](https://github.com/icebearwillhuntthemdown/TIL-Today-I-Learnt/blob/master/Kotlin/DSL.md)과 

## To Check Back Later
- Unit return type
- receiver
- suspending functions

## `it` keword : implicit name of a single parameter

If the compiler can figure the signature out itself, it's allowed not to declare the only parameter and omit `->`. The parameter will be implicitly declared under the name `it`.


## References
- https://kotlinlang.org/docs/reference/lambdas.html
