---
layout: post
title:  "Intro To React"
date:   2018-03-01 12:42:01 +1100
categories: Javascript CodeSchool Notes
tags: Javascript CodeSchool Notes
---

As I have a basic knowledge of react I have decided to do the react course on [Code School](http://campus.codeschool.com/courses/powering-up-with-react) and document my notes.

####Creating a component
* `class StoryBox extends React.Component` extends a react component. The StoryBox class must then contain a render function
* `render() { return <JSX> }` is used to return the renderable JSX 
* `ReactDOM.render(<StoryBox />, document.getElementById('story-app))` method is called to render components to a web page. It takes 2 arguments, the component and the target element.
* `react.js` and `react-dom.js` are the react components and `babel.js` converts to ES2015

####Understanding JSX (JavaScrip XML)
* Elements that are all lower case are HTML elements i.e. `<div>`
* Elements that are capitalized are react components i.e. `<StoryBox />`
* Transpiled JSX becomes a React.createElement call
* React uses className in JSX instead of class as class is a reserved JS keyword
* Any code written in curly braces gets interpreted as literal JS
* ***gotcha*** The start of the JSX must be on the same line as the `return` otherwise semicolon insertion will piss you off

###Building an App
####Props
* Arguments send to components are called **props**. They are similar to regular HTML elements
* `this.props` can be used in the components to read the arguments passed

####Passing Dynamic Arguments
* Underscores are the conventions used to distinguish custom methods from React methods
* Custom methods can be called from the `this` keyword from inside JSX i.e. `{this.customMethod(customArg)}`
* Unique keys are good practice when creating multiple components of the same type, they also help with _performance_
* `Array.map()` is used to iterate through a list and create JSX for each of it's elements: i.e. `commentList.map(c => <Comment author={c.author} body={c.body} key={c.id}/>);`


