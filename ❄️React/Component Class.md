# Component
Components are like JS **functions** for accepting arbitrary inputs(props) and return React elements describing what should appear on the screen.  

A component can be either 1)class, or 2)function, but the same rules are applied in both cases   
1. the name starts with a capital letter in both cases  
2. returns a React element(jsx)  

## Class component
```Javascript
class someComponent extends React.component{

```
<br/><br/>

## functional component
functional components don't have access to state and lifecycle methods.(as they are part of a class). functional components are only for render() purpose, so it takes props and returns jsx.

+) break down components : the smaller, more reusable. break down components so that they only implement one small thing.
<br/><br/>


```javascript
import React from 'react';
import logo from './logo.svg';
import './App.css';

function App() {
  return (
    <div className="App">
      <header className="App-header">
        <img src={logo} className="App-logo" alt="logo" />
        <p>
          Edit <code>src/App.js</code> and save to reload.
        </p>
        <a
          className="App-link"
          href="https://reactjs.org"
          target="_blank"
          rel="noopener noreferrer"
        >
          Learn React
        </a>
      </header>
    </div>
  );
}

export default App;
```
<br/><br/>

By using **Component** class we get the access to **state**, which a JS object with properties we can access at any point inside the class.

```javascript
import React, { Component } from 'react';
import logo from './logo.svg';
import './App.css';

class App extends Component {
  constructor(){
    super();

    this.state = {
      string : 'Hello, Icebear'
    }
  }

  render(){
    return (
      <div className="App">
        <header className="App-header">
          <img src={logo} className="App-logo" alt="logo" />
          <p>
          {this.state.string}
          </p>
          <button onClick = {() => this.setState({string : 'Icebear enjoys basking'})} >Change text</button>
        </header>
      </div>
    );
  }
}

export default App;
```
