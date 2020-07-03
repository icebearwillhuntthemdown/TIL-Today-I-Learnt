# Control Flow Statements
아주 기초적인 요소지만, 분명 내가 모르고 지나친 내용이 있을 것 같아 복습할 겸 정리한다. 안다고 자만하지 말기! 

1. Switch : To test **a certain variable** for multiple values

### Syntax
```java
Switch(varToValidate){
  case condition1 :
    //statements
    break;
  case condition2 :
    //statements
    break;
  case condition3: case condition4: case condition5:  //able to concatenate! 
    //statements
    break;
  default:
    //statements
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
                if (((year % 4 == 0) && !(year % 100 == 0)) || (year % 400 == 0))
                    numDays = 29;
                else
                    numDays = 28;
                break;
            default:
                System.out.println("Invalid month.");
                break;
        }
        System.out.println("Number of Days = " + numDays);
    }
}
```

2. For
### Syntax
```java
for(init; condition; iteration step){
  //statements
}
```
:bulb: Iteration step is not necessarily one. It can be any number e.g.) i += 2

3. While
4. Do While
