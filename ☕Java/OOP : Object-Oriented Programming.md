# OOP : Object-Oriented Programming

### Object
A software object stores its **state** in fields, a.k.a variables, and expose their **behaviour** with method 
<br/>

### Class
A template, or blueprint for creating objects.
```java
public class Camera{
  private String brand;
  private String model;
  private int launchYear;
  
  public void setBrand(String brand){
    this.brand = brand;
  }
  
  public String getBrand(){
    return this.brand;
  }
}
```
```java
public class Main{
  public static void main(String args[]){
    Camera myCamera = new Camrera();
    myCamera.setBrand("sony");
    System.out.println("My camera is made by " + mine.getBrand());
    //My camera is made by sony
  }
}
```
##### Class, Instance, and Reference
A good metaphor to explain the concepts of class, instance, and reference.
* Class : A blueprint for a house. You can build as many houses as you want based on this.
* Instance : The house you built with the blueprint.
* Reference : A piece of paper on which the address of the house is written, which means multiple references can point the same object.

<br/>

### 🔵 [Encapsulation](https://www.tutorialspoint.com/java/java_encapsulation.htm) 캡슐화
To wrap fields and methods together as a single unit and keep them safe from outside interference
* One of **the four fundamental OOP concepts**, the rest are inheritance, polymorphism, and abstraction. 
* The fields will be hidden from other classes using **private** keword, 
* And can only be accessed through the methods of the class, which are **getters and setters(public)**.
* Encapsulation makes the fields of a class can be made read-only and write-only,
* So that a class can have total control over what is stored in its fields.
<br/>

### Constructor
A method called to initialise a newly created object, without any return value but an instance of current class.
```java
public class Camera{
  private String brand;
  private String model;
  private int launchYear;
  
  public Camera(){
    this("Generic Brand", 2020); //constructor invocation
  }
  
  public Camera(String brand, int launchYear){  //Constructors can be overloaded
    this.brand = brand;
    this.launchYear = launchYear;
  }
}
```
* A constructor can be called from another
* Constructor can be overloaded, meaning there can be multiple of them with difference in parameters
* Return within a constructor works like break in loops

<br/>

##### :bulb: [THIS keyword](https://docs.oracle.com/javase/tutorial/java/javaOO/thiskey.html) : constructor invocation, constructor chaining
From within a constructor, you can also call **another constructor in the same class**, using the **this** keyword. The compiler determines which one to call, based on the parameters.

:heavy_check_mark: Good practice : To do initialisation in certain constructors and then call them from the default constructor, so that you don't have to write repetitive codes. 

+) to invoke(n.invocation) : to cite or appeal to so or sth as an authority for an action or in support of an arguement. 우리말로 하면 가져다 쓰다, 근거로 들다, 호출하다 정도.

<br/>

### 🔵Inheritance : Is-A Relationship
The mechanism by which one class is allowed to inherit the fields and methods of another class, using **extends** keyword, to improve reusability. The class whose features are inherited is called **Superclass(Parent class)** and the inherting class is **Subclass(Child class)**.

```java
public class Shape{
  private int x;
  private int y;
  
  public Shape(int x, int y){
    this.x = x;
    this.y = y;
  }
}

public class Rectangle extends Shape{
  private int width;
  private int height;
  
  public Rectangle(int x, int y){
    this(x, y, 0, 0); //calling the other constructor, constructor chaining
  }
  
  public Rectangle(int x, int y, int width, int height){
    super(x, y);  // calling the parent method constructor
    this.width = width;
    this.height = height;
  }
}
```
❗ Inheritance is a powerful yet overused and misused mechanism. Think carefully and consider using composition instead.  
➕ An amazing material [here](https://www.baeldung.com/java-inheritance-composition) comparing inheritance and composition
➕ Every class inherits java.lang.Object, making it the **root class** in Java 

##### Super and This
* super : refers to the parent class members(fields and methods).
  * commonly used with method overriding
  * to differentiate the inherited method with overriden method.
  * super() is used to call parent constructor
* this : refers to the current class members(fields and methods). *this* holds the reference to current instance
  * used when there's a parameter with the same name as an instance variable
  * hence, commonly used in constructors and setters, but optional in getters
  * this() is used to call another constructor in the current class

➕ Super and This can be used anywhere in a class except static areas.    
➕ super() and this() cannot be used together in the same constructor. 

<br/><br/>

### 🔵Composition : Has-A Relationship
Composition allows us to model objects that are **made up of other objects**. The objects that compose or are contained by one object are destroyed too when that object is destroyed.

```java
public class Computer{
  private Case theCase;
  private Monitor theMonitor;
  private Motherboard theMotherboard;
  
  public Computer(Case theCase, Monitor theMonitor, Motherboard theMotherboard){
    this.theCase = theCase;
    this.theMonitor = theMonitor;
    this.Motherboard = theMotherboard;
  }
}
```
❗ In every scenario where it's possible to establish a semantically correct 'has-a' relationship between a given class and others, the composition is the right choice to make.

<br/><br/>

### 🔵Polymorphism : Many + forms
The mechanism that allows methods to function differently based on the object that the method is referenced by(Assigning different functionality depending on the type of object). Polymorphism allows you to define one interface and have multiple implementations.

* Static/Compile time polymorphism : method overloading
* Dynamic/Runtime polymorphism : a.k.a dynamic method dispatch. method overriding

➕ **Upcasting**
You can use a superclass variable to refer to a subclass object.
```java
class Animal{
  void makeSound(){System.out.println("An animal makes some sound");
}
class Dog extends Animal{
  void makeSound(){System.out.println("A dog barks!");
}

class Cat extends Animal{
  void makeSound(){System.out.println("A cat meows and hisses!")
}

Animal doggo = new Dog(); // upcasting
doggo.makeSound();  // "A dog barks!", overriden

Animal cat = new Cat(); // upcasting
cat.makeSound(); //"A cat meows and hisses!", overriden
```





