# Reg ex 정규표현식 
## Creating a reg ex object
1. Regex contructor
    `Regex("a[bc]+d?")`
2. toRegex 
    `"a[bc]+d?".toRegex()`
3. static factory method
`Regex.fromLiteral("a[bc]+d?")`



## Character
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

## Ref
- https://www.baeldung.com/kotlin-regular-expressions
- https://regexr.com/
