# Fetch API

`fetch()` is a way of sending requests to the server and load new information whenever it's needed. Fetch provides a generic definition of `Request` and `Response` objects. This will allow them to be used wherever they are neede in the future. 
<br/><br/>

## Syntax
```javascript
let promise = fetch(url[, options]);
```
* url : the URL to access to the resource
* options : optional. method, headers etc.
<br/><br/>

## Response methods
`Response` provides multiple promise-based methods to access the body in various formats.
* response.text() : returns the response as text
* response.json() : parses the response as JSON
* response.formData() : returns the response as `FormData` object
* response.blob() : returns the response as Blob
* response.arrayBuffer() : returns the response as ArrayBuffer
<br/><br/>

## Example
```javascript
 fetch('https://jsonplaceholder.typicode.com/users')  //the url to access to the data
      .then(response => response.json())   // parses the response into JSON
      .then(usersInJson => console.log(usersInJson))   // logs the users in the console
```
<br/><br/>

## References
* [Javascript Info](https://javascript.info/fetch)
* [MDN](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API)
