# Method Overloading

### Definition
To create multiple methods of the same name, with different arguements and implementations.

### Why method overload?
  * improves code readability and re-usability
  * easier to remember one method name instead of multiple names
  * achieves consistency in naming
  * gives the flexibility to call a similar method with different types of data
  
### Example
![Example of method overloading](/imgs/sysout.jpg)  
System.out.println() is actually a good example of method overloading.
There are 10 methods of the same name that take different arguments.

### Little Challenge
```java
/*Instruction
Create two methods with the same name that converts feet and inches to centimeters, one with two parameter feet and inches, 
and the other with just inches. Use the former one in the latter one to calculate.
*/

public class overLoading {
    public static void main(String[] args) {
        System.out.println(calcFeetAndInchesToCentimeters(6,5)); //195.57999999999998
        System.out.println(calcFeetAndInchesToCentimeters(100)); //254.0

    }

    public static double calcFeetAndInchesToCentimeters(double feet, double inches){

        if(feet >= 0 && (inches >= 0 && inches <= 12)){
            double inchesToCent = inches * 2.54;
            double feetToCent = feet * 12 * 2.54;

            return feetToCent + inchesToCent;
        }

        return -1;
    }

    public static double calcFeetAndInchesToCentimeters(double inches){
        if(inches >= 0){
            //calc how many feet are in the inches
            //1 foot = 12 inches, 1 inch = 2.54cm;
            double numberOfFeet = (int) inches / 12;
            double remainderInches = (int) inches % 12;

            return calcFeetAndInchesToCentimeters(numberOfFeet, remainderInches);
        }

        return -1;
    }
}
```
<br/><br/>
# Method overriding
### Definition
Defining a method in a subclass that already exists in the superclass with the same signature(name and parameters)

### Why Method Overriding?
Polymorphism

### Features
* must have the same name and parameters with the overriden method
* return type must be the same or covariant return type(subtype of the return type of the overriden method)
* constructors, private, final methods can't be overriden

<br/><br/>
# Summary
요약하면, 메소드 오버로딩은 같은 이름을 가졌지만 서로 다른 메소드를 활용하는 것,  
메소드 오버라이딩은 하나의 메소드를 상속을 통해 보다 다양하게 활용하는 것으로 정리할 수 있겠다.

Method overloading | Method overriding
-------------------|------------------
To reuse a method name | To override a derived method
Usually in a single class but also in a child class | Always in two classes in a Is-a relationship
Must have different paratmeters | Must have the same signature(name and parameters)
May have different return types | Must have the same return type or covariant return type
May have different access modifiers | Must not have a lower modifier but may have a higher modifier
May throw different exceptions | Must not throw a new or broader checked exception

+)Is-a relationship : a relationship where one class is a subclass of another class, making it a superclass  
+)Covariant return type : the return types of the overriding methods will be subtypes of the return type of the overridden method
