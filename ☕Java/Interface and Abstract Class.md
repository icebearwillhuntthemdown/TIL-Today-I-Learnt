# Interface and Abstract Class

## Interface
Methods that a particular class that implements the interface must implement with **implements** keyword. Interface itself is **abstract** meaning there's no code inside the methods' code blocks, but only method signatures(name and parameters). 

### Why use Interface?
To standardise the way of a particular set of classes is used. Interface is used to provide a common behaviour that can be used by several classes by having them all implement the same interface. Access modifier is not necessary as its methods are meant to be implemented in other classes.

### Naming convention
Put an I at the beginning of the name. e.g.)ITelephone, IUser

### Program to an Interface
[StackOverFlow](https://stackoverflow.com/questions/383947/what-does-it-mean-to-program-to-an-interface)에서 본 아주 좋은 자료
```java
List myList = new ArrayList();  // programming to the interface, good practice
ArrayList myList = new ArrayList(); // not a good practice

public List myMethod(Map map);  // programming to Interface, good practice
public ArrayList myMethod(HashMap map); // not a good practic
```
Program to an Interface를 우리말로 뭐라고 번역하는지 모르겠는데, 요지는 인스턴스를 선언할 때 클래스 대신 인터페이스를 타입으로 사용하면, 이를 구현하는 클래스로 자동 형변환을 해주기 때문에 보다 유연한 프로그래밍이 가능하다는 것. 상속의 Upcasting과 유사해서 구현체 클래스의 멤버변수에 접근하려면 명시적 형변환을 하면 된다. <br/> 예를 들어, 위의 코드에서 ArrayList를 LinkedList로 바꿔야 하는 상황을 가정해보자. 아래의 경우는 앞뒤의 ArrayList를 둘 다 수정해야 하지만, 위의 경우는 뒤만 수정하면 된다. ArrayList, LinkedList 모두 List interface를 implement하기 때문에 자동으로 Type casting 되므로 일단 List 타입으로 선언해두면 어느 것으로 구현할지는 나중에 결정할 수 있다. 아래 메소드의 경우도 마찬가지로, 리턴타입과 매개변수를 일단 인터페이스로 선언해두고 어느 것으로 구현할 것인지는 메소드 내부에서 처리하면 된다. 

### Examples
Linked List, Array List implements List interface, meaning they all have the methods defined in List interface.

