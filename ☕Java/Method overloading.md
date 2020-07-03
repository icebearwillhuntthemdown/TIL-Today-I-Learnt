# Method Overloading

### Definition
To create multiple methods of the same name, with different implementations.

### Why method overload?
  * improves code readability and re-usability
  * easier to remember one method name instead of multiple names
  * achieves consistency in naming
  * gives the flexibility to call a similar method with different types of data
  
### Example
System.out.println() is actually a good example of method overloading.
There are 10 methods of the same name that take different arguments.




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
