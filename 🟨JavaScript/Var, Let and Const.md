# Var, Let and Const

## Var
* Scope : global or function scoped a.k.a current execution context scoped
* Flexibility : can be reassigned and redeclared whenever
* Initialising : optional

### Hoisting
Javascript hoists any sort of declaration on the topmost scope as possbile. In other words, JS internally declares a variable or a named function on the top of the scope. So even when a variable is refenced without being yet declared no error occurs but just returns undefined.
```javascript
(function i(){
    console.log(a);   // error doesn't occur, but returns undefined
    var a = 'icebear';
    console.log(a);   // icebear
})();
```
<br/><br/>

## Let & Const
As of ES6, let and const, the new ways of variable declaration have been introduced. 

### Let
* Scope : block scoped
* Flexibility : can be reassigned but cannot be redeclared in the same scope
* Initialising : optional

### Const
* Scope : block scoped
* Flexibility : cannot be reassigned or redeclared in the same scope
  * Value is mutable : can be modified or added
  * Reference is immutable 
* Initialising : mandatory on creation

### TDZ : Temporal Dead Zone
Hoisting **does** happen with let and const, but **uncaught reference error occurs** when they are referenced without declaration. Because there's the temporal dead zone, where they are declared but not set to undefined like var is nor initialised.
```javascript
(function i(){
    console.log(a);   // error occurs, as it's not set to undefined nor initialised.
    let a = 'icebear';
})();
```
<br/><br/>

## Conclusion
Prefer const over let, let over var, and try never to use var.

<br/><br/>

## References
* https://www.youtube.com/watch?v=dzEieWaOJE0
* https://www.youtube.com/watch?v=j-9_15QBW2s
* https://dev.to/sethusenthil/var-vs-let-vs-const-1cgc
