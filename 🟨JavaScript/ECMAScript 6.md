# ECMAScript 6 

Transpiling : Trans- + Compiling
	* The process of converting code to a format that can be read by a browser
	* Converts ES6 code to ES5
	* Used in CoffeeScript and TypeScript
	* Babel.js is widely used

to automate the process of using Babel, we use Webpack, the build tool to load all the necessary dependencies.

## ES6 Syntax

### Let and Const

### Template String
* Syntax
	- ``
	- ${} for dynamic contents

* Example
```javascript
let score = 100;
console.log(`Your score is ${score}`) //Your score is 100

```
 
### Spread Operator 전개구문
allows an iterable such as an array expression or string to be expanded as literals.

* Syntax
	- ...(array)

* Example
```javascript
let someColors = ['red', 'blue', 'white'];
let colors = ['orange', 'yellow', ...(someColors)];
console.log(colors) //["orange", "yellow", "red", "blue", "white"]
```

### Map
Map is a collection that holds **key-value** pairs and remembers the original insertion order of the keys. Any value (both objects and primitive values) may be used as either key or a value.

* Syntax
	- `let myMap = new Map()`

* Comparison with Objects
Maps and Object both holds key-value pairs but there are some differences
	- Type of Keys : keys in objects are stringified whereas keys in a Map can be any type
	- Insertion order : The keys in Map are ordered
	- Size : The number of items in a Map can be retrieved from its size property
		+ `map.size`
	- Iteration : A Map is an iterable, unlike an object

* Methods
	- Constructor
		`let a = new Map()`
		`let a = new Map([])`
	- map.size : returns the number of elements in a Map object
	- set(key, value)
	- get(key)
	- has(key)
	- delete(key)
	- clear() : removes all elements
	
	Iteration methods
	- map.keys() : returns a new Iterator object that contains the keys for each element in the Map object in insertion order.
	- map.values() : returns a new Iterator object that contains the values for each element in the Map object in insertion order.
	- map.entries() : returns a new Iterator object that contains the [keys, value] pairs for each element in the Map object in insertion order.

* Iteration
	- `for ... of` Loop 
	- `forEach()`


### Sets
`Set` is a collection that can hold any type of values, whether primitive types or ojbect references, but each element must be unique

* Syntax 
	- `let a = new Set();`

* Features
	- Duplication ommision : can be used to remove the duplicates from an array or a string
		```javascript
		const numbers = [1,1,2,2,2,3,3,3,4,4,4,4,4,5,5]
		console.log([...new Set(numbers)]) // [1,2,3,4,5]

		let text1 = 'Firefox'; 
		let text2 = 'firefox'; 
		console.log(new Set(text1)) ////Set(7) [ "F", "i", "r", "e", "f", "o", "x" ]	
		console.log(new Set(text2)) //Set(6) [ "f", "i", "r", "e", "o", "x" ]
		```

* Methods
	- Constructor : new Set([iterable])
		`let a = new Set()`
		`let a = new Set([1, 2, 3, 4, 5])`
	- set.size : returns the number of elements in a Set object
	- add(value)
	- has(value)
	- delete(value)
	- clear() : removes all elements

	Iteration methods
	- set.keys() / set.values() : returns a new Iterator object that contains the values for each element in the Set object in insertion order.  
	- set.entries() : returns a new Iterator object that contains the [value, value] pairs for each element in the Set object in insertion order.

### For... Of Loop
```javascript
let colors = ['red', 'green', 'blue'];
for(let c of colors){
	console.log(c, "is one of the primary colors")
}
```


## ES6 Functions & Objects
### Default function parameters
```javascript
function printPlan(what = "pet my meow", when = 2){
	console.log(`Today I'm going to ${what} at ${when}`)
}
printPlan(); // Today I'm going to pet my meow at 2
printPlan("walk my dog", 7); //Today I'm going to walk my dog at 7

```

### arrow function 

### enhancing object literals
a property which has a function value can be shortened.
```javascript
const obj1 = {
	foo : function(){},
	bar : function(){}
}

//below is identical but shortened version of above
const obj2 = {
	foo(){},
	bar(){}
}

let cat = {
	meow(times){
		console.log("meow".repeat(times));
	},
	purr(times){
		console.log("purr".repeat(times));
	},
	snore(times){
		console.log("snore".repeat(times));
	}
}

cat.meow(3); //meowmeowmeow
cat.purr(4); //purrpurrpurrpurr
cat.snore(2); //snoresnore
```

### destructuring assignment for arrays and objects

## ES6 Classes
### Declarations
1. class declaration
```javascript
	class Rectangle{
		constructor(height, width){
			this.height = height;
			this.width = width;
		}
	}
```

2. class expression
Class expressions can be named or undnamed. 
```javascript
let Rectangle = class{
	constructor(height, width){
		this.height = height;
		this.width = width;
	}
};
console.log(Rectangle.name); // Rectangle

let Rectangle = class Rectangle2{
	constructor(height, width){
		this.height = height;
		this.width = width;
	}
};
console.log(Rectangle.name); // Rectangle2

```

### Methods
1. Constructor : There can only be one special method with the name `constructor` in a class. If a class contains more than one occurrence of a `constructor` method `SyntaxError` error will be thrown.

2. Instance Methods
```javascript
class Rectangle{
	//constructor declaration
	constructor(height, width){
		this.height = height;
		this.width = width;
	}

	//method declaration
	printInfo(){
		console.log(
			`height : ${this.height}\nwidth : ${this.width}\narea : ${this.height * this.width}`
		);
	}
}
```

3. Getters and Setters
available for objects and classes
```javascript
class Rectangle{
	//constructor declaration
	constructor(height, width){
		this.height = height;
		this.width = width;
	}

	//method declaration
	printInfo(){
		console.log(
			`height : ${this.height}\nwidth : ${this.width}\narea : ${this.height * this.width}`
		);
	}
	//getter
	get getHeight(){
		return this.height;
	}
	//setter
	set setHeight(height){
		this.height = height;
	}
}
```

### Inheritance
```javascript
class Square extends Rectangle{
	constructor(){
		super(100,100);
	}
}

let blueSquare = new Square();
blueSquare.printInfo();
```

## TIL
- Iterables
- Array() Constructor
	- new Array(el0, el1, el2, el3) : creates a new array with the given elements
	- new Array(arrayLength) : creates an empty array with the given length 
- console.log(a,b) // console.log concatenates the arguments with a whitespace in between them


## References
- [LinkedIn Learning](https://www.linkedin.com/learning/learning-ecmascript-6)
