# Regular Expressions 정규표현식 

## Creating a regex object
1. Regex contructor   
`Regex("a[bc]+d?")`

```Kotlin
val regex = Regex("^.+@gmail.com$")             // matches gmail address 
regex.matches("icebear@gmail.com")              // true
regex.matches("icebear@someotherdomain.com")    // false
```    
<br/>

2. toRegex()  
`"a[bc]+d?".toRegex()`

```Kotlin
val regex = "[a-zA-Z0-9]+".toRegex()
regex.matches("icebear")                        // true
regex.matches("hibbie jibbies")                 // false
regex.matches("IcebearWillHuntThemDown")        // true
regex.matches("ice-bear-likes-basking")         // false
```
<br/>

3. fromLiteral()
`Regex.fromLiteral("a[bc]+d?")` 위의 두 경우와 다르게 파라미터로 넘긴 문자열을 순수 리터럴로 취급한다.  

```Kotlin
val regex = Regex.fromLiteral("[a-zA-Z]+")
regex.matches("abc")               // false
regex.matches("[a-zA-Z]+")         // true
```
</br></br>

## Characters
- \+ : matches 1 or more of the preceding token
- \* : matches 0 or more of the preceding token
- ^ : the beginning of a string / opposite
- $ : the end of a string
- [abc] : includes specified character set
- [^abc] : excludes specified character set
- [a-g] : range between specified characters
- . : includes any character except linebreaks
- \w : includes any character, alphanumeric & underscore
    + equivalent to [A-Za-z0-9_]
- \W : opposite of \w
    + equivalent to [^A-Za-z0-9_]
- \d : includes any digit character. [0-9]
- \D : opposite of \d. [^0-9]
- \s : matches any whitespace character. spaces, tabs, line breaks.
- \S : opposite of \s
</br></br>

## Ref
- https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.text/-regex/
- https://www.baeldung.com/kotlin-regular-expressions
- https://regexr.com/
- https://stackoverflow.com/questions/336210/regular-expression-for-alphanumeric-and-underscores
- https://www.geeksforgeeks.org/kotlin-regular-expression/
