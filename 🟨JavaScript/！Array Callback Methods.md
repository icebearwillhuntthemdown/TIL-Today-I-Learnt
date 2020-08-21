# Array Callback Methods

### forEach  
Performs specified action for each element in an array.

```javascript
const numbers = [1,2,3,4,5];

// anonymous function
numbers.forEach(function(num){
  console.log(num * 2);    // 2/4/6/8/10
});

// named function
numbers.forEach(printTriple);   // 3/6/9/12/15

function printTriple(num){
  console.log(num * 3);   
}
```
<br/><br/>

### map
Calls a defined callback function on each element of an array, and returns a new array that contains the results. As it creates a new array, the original array doesn't change.
```javascript
const num = [1,2,3,4,5];

const evenObject = num.map(function(n){
  return {
    number : n,
    isEven : n % 2 === 0
  }
});

// returns a new array
[{number: 1, isEven: false}, {number: 2, isEven: true}, {number: 3, isEven: false},
{number: 4, isEven: true}, {number: 5, isEven: false}]
```
<br/><br/>

### find
Returns the value of the first element in the array that satisfies the provided testing function that returns boolean. No matter how many elements matches the condition it only returns the first one element and stops.
```javascript
let movies = [
  "A single man",
  "Kingsman",
  "Suspria"
];

let movieWithoutMan = movies.find(movie => !movie.includes('man'));
console.log(movieWithoutMan); // Suspiria
```
<br/><br/>

### filter
Creates a new array with all elements that pass the test implemented by the provided funtion. It's useful when implementing search box with filters.
```javascript
const nums = [1,2,3,4,5];
const odds = nums.filter(n => n % 2 === 1);
console.log(odds);

// implementing a search box
const myFavMovies = [
    'A single man',
    'Kingmans',
    'The man from Earth',
    'Suspiria',
    'Madmax'
  ]
  
const query = 'man';
const result = myFavMovies.filter(movie => movie.toLowerCase().includes(query));
console.log("search result : " + result); // search result : A single man,Kingmans,The man from Earth 
```
<br/><br/>

### every & some
every() tests whether all elements in the array pass the provided test function while some() tests any of the elements pass the test function. Both returns a boolean value. 
```javascript
const nums = [1,3,5,7,10];
const allEven = nums.every(n => n % 2 === 0); // false
const anyEven = nums.some(n => n % 2 === 0); // true
```
<br/><br/>

### sort
sort() mutates an array in lexicographic order. When you need to organise a numeric array in ascending or descending order you can pass in a compare function as a callback.  

When `arr.sort(compareFunc(a,b));` returns
* negative : sort a before b
* 0 : unchanged
* positive : sort b before a

**Conclusion**
* asceding : `array.sort((a,b) => a-b);`  
* descending : `array.sort((a,b) => b-a);`

```javascript
const numArr = [100, 25, 4.44, 71, 9];
const lex = numArr.slice().sort();
const asc = numArr.slice().sort((a,b) => a-b);
const desc = numArr.slice().sort((a,b) => b-a);

console.log(lex); // [100, 25, 4.44, 71, 9]
console.log(asc); // [4.44, 9, 25, 71, 100]
console.log(desc); // [100, 71, 25, 9, 4.44]
```

**💡tip**
`sort()` mutates the original array, so to keep the original unchanged you can copy it with `slice()` and call `sort()` on the copy. 

<br/><br/>

### reduce
Executes a reducer function on each element of the array, resulting in a single value.
<br/>
**Syntax**
`arr.reduce((accumulator, currentValue), initialValue);`
* accumulator : holds the previous return value
* currentValue : the current element being processed
* initialValue : optional. The initial value of accumulator. If not provided, the first element in the array is being used instead.

```javscript
// Finding the maximum
const grades = [71, 76, 58, 99, 100, 45];
const max = grades.reduce((max, currVal) => {
  if(currVal > max) return currVal;   // the returned currVal now becomes the next max
  return max;
}); // 100

// one-line with Math.max()
const max = grades.reduce((max, currVal) => Math.max(max, currVal));

// Factorial calculation
const fNum = [1,2,3,4,5,6];
const facto = fNum.reduce((acc, curr) => acc * curr);
console.log(facto); // 720
```
