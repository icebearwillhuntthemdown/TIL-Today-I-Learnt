# Arrow Function
Arrow function is a syntatically compact alternative to a regular function expression. Arrow functions omit the `function` keyword and use `=>` arrow.

```javascript
// regular function expression
const square = function(n){
  return n * n;
}
square(2); // 4

// arrow function expression
const square = (n) => {
  return n * n;
}
square(3); // 9
```

### Rules
* Omit `function` keyword
* Use `=>` symbol
* `()` are optional only when there's one parameter
* But `()` are necessary when passing multiple parameters or no parameter 
