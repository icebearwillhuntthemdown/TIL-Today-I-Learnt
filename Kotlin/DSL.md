# DSL: Domain Specific Languages
- languages specialized for a specific part of an app
- DSL makes the code more readable, almost like a spoken language
- to make a DSL : to change the syntax of that specific part of the code
    + using lambda
    + extension functions
    + remove boilerplate code
    + Gradle is a good example

## Lambda
- lambda-type syntax
    + (param, param) -> returnType
    + use Unit as return type when it's void
- using lambda
    + {param, param -> behaviour}
- inferring lambda parameters
    + when a lambda has only one parameter it's inferred as it
- lambdas outside of parentheses
    + to move the lambda arguement outside of parentheses if it's the last parameter
    + if it's the only parameter, you can completely remove the parentheses
```Kotlin
fun onClick(action: () -> Unit) { ... }

// below are all compilable
view.onClick({ toast(it.toString())} )
view.onClick() { toast(it.toString()) }     
view.onClick { toast(it.toString()) }   // Kotlin convention
```

## Extension functions/properties
https://kotlinlang.org/docs/tutorials/kotlin-for-py/extension-functionsproperties.html


References
- https://www.raywenderlich.com/2780058-domain-specific-languages-in-kotlin-getting-started#:~:text=To%20make%20a%20DSL%20means,internal%20implementation%20from%20the%20user.
- https://stackoverflow.com/questions/53375316/lambda-argument-should-be-moved-out-of-parentheses
