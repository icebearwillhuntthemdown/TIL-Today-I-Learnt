# Array Callback Methods

1. forEach
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

2. map
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


3. filter, find, reduce, some, every, includes
