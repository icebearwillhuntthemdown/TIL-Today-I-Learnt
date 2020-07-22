# Interface and Abstract Class

## Interface
Methods that a particular class that implements the interface must implement with **implements** keyword. Interface itself is **abstract** meaning there's no code inside the methods' code blocks, but only method signatures(name and parameters). 

### Why use Interface?
To standardise the way of a particular set of classes is used. Interface is used to provide a common behaviour that can be used by several classes by having them all implement the same interface. Access modifier is not necessary as its methods are meant to be implemented in other classes.

### Naming convention
Put an I at the beginning of the name. e.g.)ITelephone, IUser

### Program to Interface
```java
List myList = new ArrayList();  // programming to the interface, good practice
ArrayList myList = new ArrayList(); // not a good practice
```
우리말로 뭐라고 번역하는지 모르겠는데, 요지는 인터페이스를 타입으로 사용하면 보다 유연한 프로그래밍이 가능하다는 것. 예를 들어, 위의 코드에서 myList를 LinkedList로 바꿔야 하는 상황을 가정해보자. 아래의 경우는 타입과 객체 둘 다 수정해야 하지만, 위의 경우는 뒤의 수정하면 된다. ArrayList, LinkedList 모두 List interface를 implement하기 때문에 자동으로 Type casting 되고, 유지보수 시 보다 유연하게 대처할 수 있다.
[StackOverFlow](https://stackoverflow.com/questions/383947/what-does-it-mean-to-program-to-an-interface)

### Examples
Linked List, Array List implements List interface, meaning they all have the methods defined in List interface.
