# Components Class

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
