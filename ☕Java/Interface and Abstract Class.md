# Interface and Abstract Class

## Abstraction
Focusing on **what needs to be done** rather than *who does it* and *how it's to be done*. When you define the required functionality without actually implementing the code block.

## Interface
Methods that a particular class that implements the interface **must** implement with **implements** keyword. Interface itself is **abstract** meaning there's no code inside the methods' code blocks, but only method signatures(name and parameters) and return type. Interface is abstract by definition so you can't use the *new* keyword, for instance, `List<String> myList = new List();`. You have to instantiate a class that implements the interface. Interface decouples the "what" from the "how" and you expect that **unrelated classes** will implement the interface.

#### Why use an Interface?
**To standardise the way of a particular set of classes is used.** Interface is used to provide a common behaviour that can be used by several classes by having them all implement the same interface. Access modifier is not necessary as **all** of its methods are **public and abstract** as they are meant to be implemented in other classes. 

#### Program to an Interface
[StackOverFlow](https://stackoverflow.com/questions/383947/what-does-it-mean-to-program-to-an-interface)에서 본 아주 좋은 자료
```java
List myList = new ArrayList();  // programming to the interface, good practice
ArrayList myList = new ArrayList(); // not a good practice

public List myMethod(Map map);  // programming to Interface, good practice
public ArrayList myMethod(HashMap map); // not a good practic
```
Program to an Interface를 우리말로 뭐라고 번역하는지 모르겠는데, 요지는 인스턴스를 선언할 때 클래스 대신 인터페이스를 타입으로 사용하면, 이를 구현하는 클래스로 자동 형변환(Implicit type casting)을 해주기 때문에 보다 유연한 프로그래밍이 가능하다는 것. 상속의 Upcasting과 유사해서 구현체 클래스의 멤버변수에 접근하려면 명시적 형변환(Explicit type casting)을 하면 된다. <br/><br/> 예를 들어, 위의 코드에서 ArrayList를 LinkedList로 바꿔야 하는 상황을 가정해보자. 아래의 경우는 앞뒤의 ArrayList를 둘 다 수정해야 하지만, 위의 경우는 뒤만 수정하면 된다. ArrayList, LinkedList 모두 List interface를 implement하기 때문에 자동으로 Type casting 되므로 일단 List 타입으로 선언해두면 어느 것으로 구현할지는 나중에 결정할 수 있다. 아래 메소드의 경우도 마찬가지로, 리턴타입과 매개변수를 일단 인터페이스로 선언해두고 어느 것으로 구현할 것인지는 메소드 내부에서 처리하면 된다. 

#### Examples
Linked List, Array List implements List interface, meaning they all have the methods defined in List interface.


## Inner Class
Nested class types
* Static nested class : mainly used to associate a class with its outer class.
* Non static nested class : inner class
* Local class : an inner class defined inside of a scope
* Anonymous class : a nested class without a class name

## Abstract Class
A class that defines methods, but do not provide an implementation of the methods, using **abstract** keyword for class and methods. Abstract methods are forced to be implemented in subclasses(just like interface does) and the implementation is left to the subclasses.  

#### Why use an Abstract Class?
To provide **a common definition of a base class** that multiple derived classes can share, for instance, commond methods or fields or required access modifiers other than public. <br/><br/> You can use an abstract class over interface, when you want to declare non static or non final fields and when you have a requirement for you base class to provide a default implementation of certain methods, but other methods should be open to being overridden by child classes.

* Abstract classes cannot be instantiated. You need a separate class that extends an abstract class.
* When an abstract class is subclassed, the subclass usually provides implementations for all of the abstract methods in its parent class.


#### Interface vs Abstract Class
###### Comparison
Interface | Abstract Class
------------|--------------
no constructor | can have constructors
can only have public static final variables | can have member variables
**implements** keyword | **extends** keyword
can implement multiple interfaces | can only extend from a single abstract class
**Has-A** relationship | **Is-A** relationship
all methods are **public** | can use **any** access modifiers for methods
all methods are **abstract** | can have **both** abstract and non abstract methods

###### When to use what?
First things first, consider whether the relationship is a Is-A or a Has-A(or can) relationship. <br/><br/>
동물, 개, 새 클래스가 있다고 가정해 보자. 개와 새 모두 동물이고 모든 동물은 먹고 숨쉰다. 따라서 동물-개와 새는 **IS-A** 관계이다. 이 경우 **추상 클래스** 동물 안에 추상 메소드 먹기(), 숨쉬기()를 선언하고 개, 새 클래스에서 상속 받는 편이 좋다.<br/><br/> 날기()는 어떨까? 새가 아니지만 날 수 있는 동물들도 있다. 날기는 새의 특성 중 하나일 뿐이다. 따라서 새와 비행은 **Has-A** 관계이고 이 경우 **인터페이스**를 쓴다. 인터페이스로 날기()를 선언하면, 새뿐만 아니라 **서로 무관한** 날다람쥐, 비행기, 잠자리 등에서도 쓸 수 있다. 앞서 인터페이스는 누가, 어떻게보다 **무엇**을 할 것인지에 초점을 맞춘다고 썼었는데 이게 바로 그 예시라고 볼 수 있겠다. 




 
