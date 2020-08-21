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
<br/>

### Rules
* Omit `function` keyword
* Use `=>` symbol
* `()` are optional only when there's one parameter
* `()` are necessary when passing multiple parameters or no parameter 
<br/><br/>


### Implicit Return
When the return is a single expression, then you can omit `{}` and `return` keyword.
```javascript
const square = n => n * n;
square(4); // 16
```
