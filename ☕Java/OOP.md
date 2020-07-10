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
<br/>

### [Encapsulation](https://www.tutorialspoint.com/java/java_encapsulation.htm)(캡슐화)
To wrap the fields and methods together as a single unit
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

##### :bulb: [THIS keyword](https://docs.oracle.com/javase/tutorial/java/javaOO/thiskey.html) : constructor invocation
From within a constructor, you can also call **another constructor in the same class**, using the **this** keyword. The compiler determines which one to call, based on the parameters.

:heavy_check_mark: Good practice : To do initialisation in certain constructors and then call them from the default constructor, so that you don't have to write repetitive codes. 

+) to invoke(n.invocation) : to cite or appeal to so or sth as an authority for an action or in support of an arguement. 우리말로 하면 가져다 쓰다, 근거로 들다, 호출하다 정도 되겠다.




