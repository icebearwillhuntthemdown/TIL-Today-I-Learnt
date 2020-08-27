# Promise

A `Promise` is a proxy for a value not necessarily known when the promise is created. It allows you to associate handlers with an asynchronous action's eventual success value of failure reason. This lets asynchronous methods **return values** like synchronous methods. Instead of immediately returning the final value, the asynchronous methods returns a promise to supply the value at some point in the future. `fetch()` is an example of Promise.
<br/><br/>

## Syntax
`new Promise(executor)`
executor is a function to be called by the constructor during the process of constructing the promise object. The executor is custom code that ties and outcome to promise and that is written by the programmer. The signature of this function is expected to be like below.
```javascript
function(resolutionFunc, rejectionFunc){
  //typically some asynchronous operation
}
```
<br/>

#### Example
```javascript
const myPromise = new Promise((resolve, reject) =>{
  if(false){
    setTimeout(() => {
      resolve('Success!');
    }, 5000);
  }else{
    reject('Failure!');
  }
});

myPromise
  .then(value => value + '!!!!')
  .then(newValue => console.log(newValue))
  .catch(rejectValue => console.log(rejectValue));
```
<br/><br/>

![MDN](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FbsGGSU%2FbtqHhRbq5mX%2FI68lpO4rX1TqpoLJtbyjEk%2Fimg.png)

## States of A Promise
* pending : initial state, not fulfilled nor rejected.
* fufilled : means that the operation succeessed and returns a value
* rejected : means that the operation failed and returns a reason(error)
<br/><br/>

## then() and catch()
`promise.then()`, `promise.catch()` are used to associate further action with a promise that becomes settled. There methods also return a newly generated **promise object** which can optionally be used for chaining.
* then() : takes 2 callback functions each for the success and failure cases of the Promise and returns a `Promise` object
```javascript
p.then(onFulfilled[, onRejected]);

p.then(value => {
  //fulfillment
}, reason => {
  //rejection
}
```
* catch() : deals with rejected cases only and returns a `Promise` object. It internally calls promise.then(undefined, onRejected). 
```javascript
p.catch(onRejected);

p.catch(function(reason){
  //rejection
});
```
<br/><br/>

## References
[MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)
