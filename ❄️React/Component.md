# Component
Components are like **functions** for accepting arbitrary inputs(props) and return React elements describing what should appear on the screen. The smaller the component, the more reusable. Break down components so that they only implement **one small thing**. 

A component can be either 1)class, or 2)function, but the same rules are applied in both cases   
1. the name starts with a capital letter  
2. returns a React element(jsx)  

## Class component
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


<br/><br/>

## Functional component
Functional components **don't** have access to state and lifecycle methods as they are parts of a class. Instead, you can use Hooks for functional components. Functional components are only for render() purpose, so it takes props and returns jsx. 
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

