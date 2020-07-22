# Interface and Abstract Class

### Abstraction
Focusing on **what needs to be done** rather than *who does it* and *how it's to be done*. When you define the required functionality without actually implementing the code block.

## Interface
Methods that a particular class that implements the interface must implement with **implements** keyword. Interface itself is **abstract** meaning there's no code inside the methods' code blocks, but only method signatures(name and parameters). Interface is abstract by definition so you can't use the *new* keyword, for instance, List<String> myList = new List();. You have to instantiate a class that implements the interface.

### Why use Interface?
To standardise the way of a particular set of classes is used. Interface is used to provide a common behaviour that can be used by several classes by having them all implement the same interface. Access modifier is not necessary as its methods are meant to be implemented in other classes.

### Program to an Interface
[StackOverFlow](https://stackoverflow.com/questions/383947/what-does-it-mean-to-program-to-an-interface)에서 본 아주 좋은 자료
```java
List myList = new ArrayList();  // programming to the interface, good practice
ArrayList myList = new ArrayList(); // not a good practice

public List myMethod(Map map);  // programming to Interface, good practice
public ArrayList myMethod(HashMap map); // not a good practic
```
Program to an Interface를 우리말로 뭐라고 번역하는지 모르겠는데, 요지는 인스턴스를 선언할 때 클래스 대신 인터페이스를 타입으로 사용하면, 이를 구현하는 클래스로 자동 형변환(Implicit type casting)을 해주기 때문에 보다 유연한 프로그래밍이 가능하다는 것. 상속의 Upcasting과 유사해서 구현체 클래스의 멤버변수에 접근하려면 명시적 형변환(Explicit type casting)을 하면 된다. <br/><br/> 예를 들어, 위의 코드에서 ArrayList를 LinkedList로 바꿔야 하는 상황을 가정해보자. 아래의 경우는 앞뒤의 ArrayList를 둘 다 수정해야 하지만, 위의 경우는 뒤만 수정하면 된다. ArrayList, LinkedList 모두 List interface를 implement하기 때문에 자동으로 Type casting 되므로 일단 List 타입으로 선언해두면 어느 것으로 구현할지는 나중에 결정할 수 있다. 아래 메소드의 경우도 마찬가지로, 리턴타입과 매개변수를 일단 인터페이스로 선언해두고 어느 것으로 구현할 것인지는 메소드 내부에서 처리하면 된다. 

### Examples
Linked List, Array List implements List interface, meaning they all have the methods defined in List interface.


## Inner Class
Nested class types
* Static nested class : mainly used to associate a class with its outer class.
* Non static nested class : inner class
* Local class : an inner class defined inside of a scope
* Anonymous class : a nested class without a class name

## Abstract Class
A class that defines methods, but do not provide an implementation of the methods, using **abstract** keyword for class and methods. Abstract methods are forced to be implemented in subclasses(just like interface does) and the implementation is left to the subclasses.

```java
public abstract class Animal
```

Abstract classes cannot be instantiated. You need a separate class that extends an abstract class.

## Interface vs Abstract Class
First things first, consider if the relationship is whether a Is-A or a Has-A(or can) relationship.

날 수 있는 것은 새뿐만이 아니다. 새가 아니지만 날 수 있는 동물들도 있다. 따라서 새와 비행은 Has-A 관계이고, 이 경우 Interface를 쓴다. 

Interface | Abstract Class
------------|--------------
cannot be instantiated, hence no constructor | can be instantiated and can have constructors
can only have public static final variables | can have member variables
**implements** keyword | **extends** keyword
can implement multiple interfaces | can only extend from a single abstract class
**Has-A** relationship | **Is-A** relationship
all methods are **public** | can use **any** access modifiers for methods
all methods are **abstract** | can have **both** abstract and non abstract methods





 
