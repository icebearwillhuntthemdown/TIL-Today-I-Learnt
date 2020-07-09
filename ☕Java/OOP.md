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
```java
public class Camera{
  private String brand;
  private String model;
  private int launchYear;
  
  public Camera(){
    this("Generic Brand", "Unknown Model", 2020); //Assign default values with 'this' keyword
  }
  
  public Camera(String brand, int launchYear){  //Constructors can be overloaded
    this.brand = brand;
    this.launchYear = launchYear;
  }
}
```
* Definition : A method called to initialise a newly created object
* A constructor can be called from another
* **this** keyword is used to assign default values to fields, but must match with all the existing ones
* Constructor can be overloaded, meaning there can be multiple of them with difference in parameters

