# Control Flow Statements

1. Switch : To test **a certain variable** for multiple values

### Syntax
```java
Switch(varToValidate){
  case condition1 :
    //code to be executed
    break;
  case condition2 :
    //code to be executed
    break;
  case condition3: case condition4: case condition5:  //able to concatenate! 
    //code to be executed
    break;
  default:
    //code to be executed
    break;
}
```

### Example
Attribution to [StackOverFlow](https://stackoverflow.com/questions/16706716/using-two-values-for-one-switch-case-statement)
```java
class SwitchDemo {
    public static void main(String[] args) {

        int month = 2;
        int year = 2000;
        int numDays = 0;

        switch (month) {
            case 1:
            case 3:
            case 5:
            case 7:
            case 8:
            case 10:
            case 12:
                numDays = 31;
                break;
            case 4:
            case 6:
            case 9:
            case 11:
                numDays = 30;
                break;
            case 2:
                if (((year % 4 == 0) && 
                     !(year % 100 == 0))
                     || (year % 400 == 0))
                    numDays = 29;
                else
                    numDays = 28;
                break;
            default:
                System.out.println("Invalid month.");
                break;
        }
        System.out.println("Number of Days = "
                           + numDays);
    }
}
```
:bulb: 복수의 조건을 연달아 쓸 수 있단 것을 알게 됐다. 

2. For
3. While
4. Do While
