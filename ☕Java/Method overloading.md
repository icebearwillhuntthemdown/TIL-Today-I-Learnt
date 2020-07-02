# Method Overloading
Using methods with the same name but with different arguments

```java
public class overLoading {
    public static void main(String[] args) {
        System.out.println(calcFeetAndInchesToCentimeters(6,5)); //195.57999999999998
        System.out.println(calcFeetAndInchesToCentimeters(100)); //254.0

    }

    public static double calcFeetAndInchesToCentimeters(double feet, double inches){

        if(feet >= 0 && (inches >= 0 && inches <= 12)){
            double inchToCent = inches * 2.54;
            double feetToCent = feet * 12 * 2.54;

            double result = inchToCent + feetToCent;

            return result;
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
