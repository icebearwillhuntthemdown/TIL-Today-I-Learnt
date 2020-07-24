# Generic Types
A generic type is a generic class or interface that is parameterised over types. 

### Generic class
```java
public class Box<T>{
  private T t;
  
  public void set(T t){ this.t = t; }
  public T get(){ return this.t; }
}
```
Generic class is defined like `class className<T1, T2, ..., Tn>{/*...*/}`. 'T1, T2, ..., Tn' that are delimited by angle brackets(<>), are **type parameters** or **type variables**. A type variable can be any class type, any interface type, any array type, only if they are **non-primitive** types. For example, we can instantiated the Box class with various types like below.

```java
Box<Integer> integerBox = new Box<>();
Box<Double> doubleBox = new Box<>();
Box<String> stringBox = new Box<>();
```
<br/>

### Why use Generic Types?
It was only after Java 1.5(a.k.a Java SE 5) that the concept of generic type was introduced. Before then, they used raw type, which is not specifying any type for the type parameter like `List myList = new ArrayList();`. The raw type method is still valid for compatibility, but it's certainly not recommended as the compiler can't check the type safety in that way. Therefore, now we specify types for type parameter or use generic types instead, like `List<String> myList = new ArrayList<>();`.

### Naming conventions
By convention, type parameter names are single, uppercase letters.
* E : Element
* K : Key
* T : Type
* V : Value
* S, U, V etc : 2nd, 3rd, 4th types. (이 알파벳들이 특정 의미를 내포하는 건 아니므로 어떤 알파벳을 써도 무관하다.)
<br/><br/>

### Invoking and Instantiating a Generic Type
```java
Box<Integer> integerBox = new Box<>();
```
To reference a generic class, you must perform a generic type invocation, which is replacing T with other concrete value, for example Integer. From Java SE7 onwards, you can omit the type argument required to invoke the constructor of a generic class, leaving only the empty angle brackets(<>), a.k.a **the diamond**.  
+) 여담이지만 그동안 생성자 타입 파라미터를 쓰는 게 맞는 건지, 비워두는 게 맞는 건지 정말 궁금했는데 드디어 알게 돼서 속시원하다. 자바 7 이후로는 비워두는 게 좋은 관행이라는 것. 역시 공부를 할수록 마음이 편해진다. 
<br/><br/>

### Type Parameter vs Type Argument
Type parameter and type argument are not interchangeable. The E in `List<E>` is a **type parameter**, which works as a **placeholder**, and the String in `List<String>` is a **type argument**, which is an **actual type** passed as an argument. You provide type arguments to create a parameterised type. 

+) A **parameterised type** is an **instantiation of a generic type** with actual type arguments.
`List<String> myList = new ArrayList<>();`
<br/><br/>

### References
* [Oracle Java Tutorials](https://docs.oracle.com/javase/tutorial/java/generics/types.html)
* [Stack Overflow](https://stackoverflow.com/questions/4073359/understanding-java-generics-type-parameter-conventions)
