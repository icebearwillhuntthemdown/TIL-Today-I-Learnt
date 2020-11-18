# Operators

## Conditionals
### Ternary Operator
```Kotlin
// In Java
Int arbitrary = a > b ? 0 : 100

// In Kotlin
arbitrary: Int = if (a > b) 0 else 100
```

### Switch and When
```Kotlin
// In Java `switch`
switch(x) {
    case 0, 1:
    System.out.println("x == 0 or x == 1");
    break;

    case 2:
    System.out.println("x == 2");
    break;

    default:
    System.out.println("x is not 0 nor 1 nor 2")
}

// In Kotlin `when`
when (x) {
    0, 1 -> println("x == 0 or x == 1")
    2 -> println("x == 2")
    else -> {
        println("x is not 0 nor 1 nor 2")
    }
}
```

### `?:` Elvis Operator : For null safety
```Kotlin
// In Java
String ar = "";
if(a != null) {
    ar = a;
} else {
    ar = b;
}

// In Kotlin
var ar = a ?: b
```

## `is` : Type check and smart cast operator
- Type checks : 특정 타입 해당 여부 확인
```kotlin
var obj: String = "some string"

if(obj is String){  // true
  println("yes, this is a string")
}

if(obj !is String){
  println("this won't be printed")
}

var obj2 = !(obj is String) // false
```

```Kotlin
// 이런 것도 된다!
when (x) {
  is Int -> println(x + 1)
  is String -> println(x.length)
  is IntArray -> println(x.sum())
}
```
- Smart casts : 자동 형변환
```kotlin
var obj: Any = "string"
if(x !is String) return
print(x.length) // 6, x is automatically cast to string
```
<br/><br/>

## `as` : Type cast operator
- **unsafe** casting  
  변환이 불가능할 경우 `ClassCastException` 에러를 던진다. 곧, 에러의 여지가 있는 불안전한 형변환.  
```Kotlin
val x: String = y as String // y가 null이면 에러 발생
```
<br/>

- **safe** casting : `as?`  
  `as?`는 형변환에 실패하면 null을 리턴한다 
```Kotlin
val x: String? = y as? String // y가 null이면 null 리턴, null이 아니면 String으로 형변환
``` 
<br/><br/>


## References
- [Kotlin](https://kotlinlang.org/docs/reference/typecasts.html)
