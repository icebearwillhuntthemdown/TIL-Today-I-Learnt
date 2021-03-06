# Kotlin Basics

## Declaration
* variables
    - var : mutable  
        `var varName : type = value`                 
    - val : read-only  
        `val valName : type = value`

* functions
```Kotlin
fun funName(arg1Name : type, arg2Name:type): returnType {
    code block to be executed...
}
```
    - void return : `Unit` or can be omitted 
<br/><br/>

## String templates
```kotlin
val i = 10
println("i = $i") // "i = 10"

val s = "abc"
println("$s.length is ${s.length}") // abc.length is 3
```
<br/><br/>


## Null Safety
Kotlin's type system is aimed at eliminating the danger of null references, hence `NullPointerException` from code. 

### Nullable `?`
A refence must be explicitly marked as nullable with `type?` when null value is possible.

```Kotlin
var a: String = "abc"   // regular initialisation means non-null by default
a = null    // compile error

var b: String? = "abc"  // declared as nullable
b = null // ok
```
<br/>

### Safe calls `?.`
If the variable on the left-hand side of `?.` is not null, then it references the variable, otherwise null.
```Kotlin
val a = "Kotlin"
val b: String? = null
println(b?.length)  // returns b.length if b is not null, otherwise returns null
println(a?.length)  // unnecessary safe call as a is not nullable
```

Safe calling can be chained.
```Kotlin
bob?.department?.head?.name
```
The chain returns null if any of the variables, `bob`, `department`, `head`, is null
<br/>

### Elvis Operator `?:`
If the expression to the left of `?:` is **not null**, the elvis operator returns it, otherwise it returns the expression to the right. The right-hand side expression is evaluated only if the left-hand side in null.
```Kotlin
// using if-else statement
val l: Int = if (b != null) b.length else -1

// using Elvis Operator
val l = b?.length ?: -1 // b가 null이 아니면 b.length, null이면 -1 
```

Using elvis operator, you can conditionally throw or return by putting them on the right-hand side of the elvis operator.
```Kotlin
fun foo(node: Node): String? {
    val parent = node.getParent() ?: return null
    val name = node.getName() ?: throw IllegalArgumentException("name expected")
}
```
<br/>

### Not Null Assertion Operator `!!`
`!!` converts any value to a non-null type and throws `NullPointerException` if the value is null.
```Kotlin
val l = b!!.length  // !! claims b is not null, if b is null then NPE occurs
```
<br/><br/>

## main()
```Kotlin
// 
fun main(args: Array<String>){
    println("Hello, World!")
}

// args can be omitted from Kotlin 1.3 and onwards
fun main(){
    println("Hello, World!")
}

//Java
public static void main(String[] args){
    System.out.println("Hello, World!")
}
```
<br/><br/>

## References
- [Kotlin](https://kotlinlang.org/docs/reference/basic-syntax.html)
