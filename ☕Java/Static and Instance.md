# Static and Instance

## Static?
The keyword static means the particular member belongs to a class itself, not to and instance of the class, so that it can be shared all instances of the class.  

## Variables

#### Local variable 
Local variable exists only inside of a method while it is being executed. Once the program reaches the end of the method, the local variable disappears from memory. The next time the method is called a completely new version of the local variable is created.

#### Instance variable(Class member)
Instance variables hold values that are associated with an individual object. Instance variables come into existence when an object is created and exist in memory until the object no longer exists.

#### Static variable(Class variable)
it means exactly a single copy of the field is created to be shared among all instance of the class. Static variables go in Metaspace of JVM memory. Static variables are useful when the value of variable is independent of objects, or when the value is supposed to be shared across all objects.


## Methods 

## Instance methods
Methods which required an object of its class to be created before it can be called.
* referenced by object name, **objectName.methodName(args)**
* stored in Permanent Generation space of heap but the parameters and their local variables and the return value are allocated in stack
* belong to the object of the class, not the to class
* every individual object has its own copy of the instance methods
* can be overriden

## Static methods
Methods can be called without creating an object of class
* referenced by class name, **className.methodName(args)**
* designed to be **shared among all objects** created from the same class
* can't be overriden but can be overloaded
* stored in Permanent Generation space of heap
* static methods are associated to the class itself, not to the objects of the class  




## References
* https://www.baeldung.com/java-static
* https://www.geeksforgeeks.org/static-methods-vs-instance-methods-java/

