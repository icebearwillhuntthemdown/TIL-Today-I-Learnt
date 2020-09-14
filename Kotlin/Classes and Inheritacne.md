# Classes and Inheritance

## Classes
class header = type parameters, primary constructor
* Syntax
```Kotlin
class Person(
    var firstName: String,  // primary constructor
    var lastName: String,
    val dateOfBirth: Int
){
    var children: MutableList<Person> = MutableListOf<>()
    constructor(parent: Person){    // secondary constructor
        parent.children.add(this)
    }
}
```
<br/>

### Constructors
A class in Kotlin can hava a primary constructor and one or more secondary constructors. The primary constructor is part of the class header: it goes after the class name(and optional type parameters).

* Primary constructor  
The concise way to initialise a class  
```Kotlin
class Person constructor(var firstName: String) {/*...*/}
```

The `constructor` keyword can be omitted when it doesn't have any annotations or visibility modifiers.  
```Kotlin
class Person(var firstName: String) {/*...*/}
```
* Secondary constructors  
Allows you to put additional initialisation logic. Secondary constructors are prefixed with `constructor` keyword.
```Kotlin
class Person(var firstName: String, var lastName: String) {
    val firstName: String
    var lastName: String
    constructor(age: Int) { /*...*/ }
}
```

* Default contructor
If a non-abstract class does not declare any constructors(primary or secondary), it will have a generated primary constructor with no arguments.
```Kotlin 
class Person {/*...*/}`
```
<br/>

### Creating instances
To create an instance of a class, we call the constructor as if it were a regular function. Kotlin does **not** have a **new** keyword.
- `val nobody = Person()`
- `val employee1 = Person("Jane", "Doe", 19910111)`
<br/>

### getter and setter
In Kotlin, getters and setters are optional and are auto-generated if you do not create them manually.

* Auto-generated
```Kotlin
class Person {
    var name: String = "defaultValue"

    // below are internally auto-generated
    //getter
    get() = field 

    //setter
    set(value){
        field = value
    }
}

fun main(args: Array<String>) {
    val person = Person()
    p.name = "jack"     // calls the setter
    println("${p.name}")    //calls the getter
}
```

* manually defining getters and setters
```Kotlin
class Person {
    var age: Int = 0
    get() = field
    set(value){
        field = if (value < 18)
            18
        else if (value >= 18 && value <= 30)
            value
        else
            value -3
    }

    var actualAge: Int = 0  // getter and setter are auto-generated
}

fun main(){
    val gaby = Person()
    gaby.actualAge = 14
    gaby.age = 15
    println("Gaby is ${gaby.actualAge} but she pretends to be ${gaby.age}")    
    //Gaby is 14 but she pretends to be 18
}
```
<br/>

### data class
Data class is a class to solely hold data. The fields go into the primary constructor parenthesis.
```Kotlin
data class User(
    var userId: String = "",
    var userName: String = "",
    var email: String = ""
)
```
<br/><br/>

## Inheritance
### `Any` : The default superclass
All classes in Kotlin have a common superclass `Any`. `Any` has three methods: `equals()`, `hashCode()`, and `toString()`.
<br/>

### `open` : Inheritable
Kotlin classes are **final by default**, meaning they can't be inherited. To make something inheritable, use the `open` keyword.
- `open class` : inheritable class
```Kotlin
open class Base(p: Int)
```

-`open var/val`, `open fun` : overridable members
You can only override `open var/val`, `open fun` functions with `override` keyword. If a member is not `open` then it can't be overridden, with or without the `override` keyword. A member marked `override` is automatically set `open`, but you can prohibit reoverriding by using `final` keyword.

```Kotlin
open class Shape{
    open val vertextCount: Int = 0  // overridable variable
    open fun draw() { /*...*/ } // overridable function
    fun fill() { /*...*/ }  // not overridable function
}

class Circle : Shape() {
    override val vertexCount = 4
    override fun draw(){ /*...*/ } 
    //final override fun draw() { /*...*/ } // finalised
}
```

+) interface members are `open` by default
```Kotlin
interface Polygon{
    fun draw() { /*...*/ }  // `open` keyword is not needed
}
```
<br/>

### `:` : extends 
To declare an explicit supertype, place the type after a `:` in the class header.
```Kotlin
open class Base(p: Int)
class SubclassOfBase(p: Int) : Base(p)
```
<br/>

### `super` : calling the superclass implementation
```Kotlin
open class Rectangle {
    open fun draw(){ println("Drawing a rectangle") }
    val borderColor: String get() = "black"
}

class FilledRectangle : Rectangle {
    override fun draw() {
        super.draw()    //deriving draw() method from the superclass
        println("Filling the rectangle")
    }

    val fillColor: String get() = super.borderColor // deriving getter from the superclass
}
```

+)`super<Base>` 
If a class inherits multiple implementations of the same member from its immediate superclasses, it must override this member and provide its own implementation. To denote the supertype from which the inherited implementation is take, we can use `super<Base>`.
```Kotlin
open class Rectangle {
    open fun draw() { /*...*/ }
}

interface Polygon{
    fun draw()
}

class Square() : Rectangle(), Polygon {
    override fun draw() {   // providing subclass's own implementation
        // using <superclass> to differentiate the superclasses
        super<Rectangle>.draw() 
        super<Polygon>.draw()
    }
}
```
<br/>

### `abstract` 
An abstract member does not have an implementation in its class. An `abstract` class or function is `open` by default. 
```Kotlin
open class Polygon{
    open fun draw() { /*...*/ }
}

abstract class Rectangle : Polygon(){
    abstract override fun draw()
}
```

