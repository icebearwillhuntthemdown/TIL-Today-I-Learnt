# Functional Programming

## what the heck is it
Do everything with functions

### DOs
- imperative style > functional style
- pure function
    - the output of a function should purely depend on the input
    - they should not rely on any outside values to produce the return value
- higher order functions : either returning other functions or taking other functions as arguments
    + taking other functions 
```javascript
const num = [1,2,3,4,5]
num.map(n => n*5)
```
    + returning other functions
```javascript
function adjectifier(adjective) {
    return function(string) {
        return console.log(`${adjective} ${string}`)
    }
}

//the function above can be simplified as below
const adjectifier2 = adjective => string => console.log(`${adjective} ${string}`)

const coolifier = adjectifier("cool")
coolifier("conference")     // "cool conference"
coolifier("icebear")        // "cool icebear"
```

### DON'Ts
- Iteration : use map, reduce, filter 
    - instead of for, while loops  
- Mutability : use immutable data
    - think of all data immutable
