# Key Concepts

**React is...**
* **Declarative**  
  Design simple views for each state in your application, and React will efficiently update and render just the right components when your data changes.
* **Component-based**  
  Since component logic is written in JavaScript instead of templates, you can easily pass rich data through your app and keep state out of the DOM.
* **Learn once, write anywhere**  
  You can develop new features in React without rewriting existing code. React can also render on the server using Node and power mobile apps using React Native.

## 4 Key Concepts of React

#### Declarative Paradigm
React is declarative. The name 'React' means whatever the state or data of the app is, it's going to **react** to it and change everything for you so that you get the display that you want.

**Declarative vs Imperative Paradigms**
* Declarative 선언형 : Just declare what the page looks like, then I'll do it!
* Imperative 명령형 : You directly changing DOMs in reponse to various user events.

#### Reusable Components
React components are reusable and shareable, so that you can build websites like lego blocks.

#### Unidirectional Data Flow
One way data flow lets easy debugging, as it means you only have to look in the place where the data exists and where the data flows through.
* State : Data. JS object that describes your app.
* JSX : HTML-like syntax inside of JS, in which React components are built.
* Virtual DOM : A tree like JS object made with state and components that gives react a blueprint of how it should update the actual DOM. React compares the virtual DOM and DOM and modifies the DOM.

#### Cross Platform : React Everywhere
React doesn't make assumptions about what technology stack you use, but only focuses with the UI. React Native for mobile apps, React 360 for VR apps, Electron and React desktop for desktop apps.
