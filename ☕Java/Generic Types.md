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
Generic class is defined like `class className<T1, T2, ..., Tn>{/*...*/}`. 'T1, T2, ..., Tn' that are delimited by angle brackets(<>), are **type parameters** or **type variables**. A type variable can be any class type, any interface type, any array type, only if they are **non-primitive** types.

### Naming conventions
By convention, type parameter names are single, uppercase letters.
* E : Element
* K : Key
* T : Type
* V : Value
* S, U, V etc : 2nd, 3rd, 4th types. (이 알파벳들이 특정 의미를 내포하는 건 아니므로 어떤 알파벳을 써도 무관하다.)

### Invoking and Instantiating a Generic Type
```java
Box<Integer> integerBox = new Box<>();
```
To reference a generic class, you must perform a generic type invocation, which is replacing T with other concrete value, for example Integer. From Java SE7 onwards, you can omit the type argument required to invoke the constructor of a generic class, leaving only the empty angle brackets(<>), a.k.a **the diamond**.


### References
* [Oracle Java Tutorials](https://docs.oracle.com/javase/tutorial/java/generics/types.html)
* [Stack Overflow](https://stackoverflow.com/questions/4073359/understanding-java-generics-type-parameter-conventions)
