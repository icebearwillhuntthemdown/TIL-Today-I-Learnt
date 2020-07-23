
# Autoboxing and Unboxing

### Definition
Autoboxing is often used to represent a primitive type in a place where primitive type is not allowed.
```java
List<int> intArrayList = new ArrayList<>(); // impossible
List<Integer> intArrayList = new ArrayList<>(); // possible
```
* Autoboxing : converting a primitive type into a wrapper class. e.g.) int -> Integer
`Integer.valueOf(int i);`
* Unboxing : converting a wrapper class into a primitive type. e.g.) Integer -> int  
`Integer.intValue();`

### Tips
Below codes don't get an error, as Java compiler is doing the hard work for you! 따봉 컴파일러야 고마워!
```java
Integer myInteger = 71;   // Integer myInteger = Integer.valueOf(71);
int myInt = myInteger;    // int myInt = myInteger.intValue();
```

### Methods
* Integer.toString(int i) : returns a String object representing the int argument.
* Integer.toString() : same as above but for the value of this Integer.
* Integer.parseInt(String s) : parses the string argument into a int.
* Integer.valueOf(int i) : returns an Integer instance representing the int value. 
* Integer.valueOf(String s) : same as above but for String value.
* Integer.intValue() : returns the value of this Integer as an int.
