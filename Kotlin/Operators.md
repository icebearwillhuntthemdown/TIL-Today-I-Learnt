# Operators

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

## `?:` : Elvis operator
[Elvis operator](https://github.com/icebearwillhuntthemdown/TIL-Today-I-Learnt/blob/master/Kotlin/Basics.md) for null safety

## References
- [Kotlin](https://kotlinlang.org/docs/reference/typecasts.html)
