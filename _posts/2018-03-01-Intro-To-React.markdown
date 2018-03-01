---
layout: post
title:  "Intro To React"
date:   2018-03-01 12:42:01 +1100
categories: Javascript CodeSchool Notes
tags: Javascript CodeSchool Notes
---

As I have only a basic knowledge of React syntax I have decided to do the react course on [Code School](http://campus.codeschool.com/courses/powering-up-with-react) to get some practical experience in using react and to document my learning.

### Creating a component
* `class StoryBox extends React.Component` extends a react component. The StoryBox class must then contain a render function
* `render() { return <JSX> }` is used to return the renderable JSX 
* `ReactDOM.render(<StoryBox />, document.getElementById('story-app))` method is called to render components to a web page. It takes 2 arguments, the component and the target element.
* `react.js` and `react-dom.js` are the react components and `babel.js` converts to ES2015

### Understanding JSX (JavaScrip XML)
* Elements that are all lower case are HTML elements i.e. `<div>`
* Elements that are capitalized are react components i.e. `<StoryBox />`
* Transpiled JSX becomes a React.createElement call
* React uses className in JSX instead of class as class is a reserved JS keyword
* Any code written in curly braces gets interpreted as literal JS
* ***gotcha*** The start of the JSX must be on the same line as the `return` otherwise semicolon insertion will piss you off

## Building an App
### Props
* Arguments send to components are called **props**. They are similar to regular HTML elements
* `this.props` can be used in the components to read the arguments passed

### Passing Dynamic Arguments
* Underscores are the conventions used to distinguish custom methods from React methods
* Custom methods can be called from the `this` keyword from inside JSX i.e. `{this.customMethod(customArg)}`
* Unique keys are good practice when creating multiple components of the same type, they also help with _performance_
* `Array.map()` is used to iterate through a list and create JSX for each of it's elements: i.e. `commentList.map(c => <Comment author={c.author} body={c.body} key={c.id}/>);`

### Handling Data Chance With State
* Components can have a constructor function `constructor() { super(); }`
* the state is a JavaScript object that lives inside the component
* The initial state of a component is in the class constructor `this.state = { ... };`
* `super()` must be called in the constructor
* `this.setState({ ... })` is used to update the state of a component
* `onClick={this._eventHandler.bind(this)}` allows the binding of events to html elements

### Synthetic Events (capturing user actions)
* synthetic events are the way React unifies the way different browsers do events 
* `ref` allows form properties to be assigned on a component object (2-way binding) i.e. `ref={(input) => this._author = input}`
* Parents components can pass callback functions as props to child components to allow two-way communication
* `this._body.value` can be used to access the value of body
* callbacks can be passed by assigned them to `props`

### Using lifecycle methods to load comments
* JQuery can be used to make ajax requests
* Need to set the initial state of the array so that it can be later populated with data from the server
* When the fetch request is complete we can use the success function to set the state of the initial object `success: (x) => { this.setState({x}) }`
* **Lifecycle methods**: lifecycle methods in React are functions that get called while the component is rendered for the first time *OR* it is about to be removed from the DOM
* Order or method calls for a component:
    1. constructor()
    2. componentWillMount()
    3. render()
    4. componentDidMount()
    5. componentWillUnmount()
* Components need to be responsible for removing any timers that they create

### Adding and Deleting on the Server Side
* Events are first from the Comment component, they are passed as a prop on the parent component. i.e. `onDelete={this._deleteThing.bind(this)}`
* make sure `event.preventDefault()` is used so that the page doesn't reload on the click
* *One-Way control flow*: control flows from higher level components down to child components, forcing changes to happen reactively.