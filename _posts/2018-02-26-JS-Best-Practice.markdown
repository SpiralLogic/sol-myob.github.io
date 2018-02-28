---
layout: post
title:  "JS Best Practice Notes"
date:   2018-02-36 16:42:01 +1100
categories: Javascript CodeSchool Notes
tags: Javascript CodeSchool Notes
---

It has been a while since I have done any major JS projects (pre 2014 😲). This means that although I have attempted to keep up to date with JS and it's developments (ES2015+) it isn't quite as easy to keep up with best practice. So this is a summary of my learning from following the CodeSchool [JS Best Practice](http://campus.codeschool.com/courses/javascript-best-practices/l) course.

#### Javascript Best Practices

##### Level 1 - Ternary Conditionals, Logical Assignments, Switch Blocks
- **Falsy Values**: false, 0, undefined, NaN, empty string, null
- **Ternaries**: Use parentheses 'condition ? true : false' to ensure the conditional is check correctly
- Multiple actions can be performed in ternaries:
`condition ? (first = "test", second = "test2") : third = "stuff"`
- **Short Circuit `||` and `&&`**: || Can be used as logical assignment to check if a property on an object exists and if it doesn't assign it. `obj.prop = obj.prop || []` set's obj.prop as an empty array if prop isn't set. If none of the values are true when using a short circuit || the last value will be assigned.
- **switch block**: allow fall through. Each `case` statement should have a `break`

##### Level 2 - Loop Optimization, Script Execution, Performance & Measuring Performance
- Assign `.length` evaluation to a cached value. This can be assigned inside the for construct `for(var i = 0, x = something.length; i < x; i++)`
- Assign lists stored on objects to a cached variable
- Stick to for loops to avoid accessing all of the array prototype properties when using `for in`
- Script tags should be as low as possible but within the body tags
- Add an async attribute to script tags to allow the remainder of the document to be loaded while the script file is loaded
- Use a prototype for shared methods for an object
- Adding individual DOM elements isn't fast and causes document reflow (this is what libraries like React solve). Using the document fragment additions can be made all at once
- Declare variables as few times as possible by declaring all variables at the same time (using commas)
- Use concatenation operator for small numbers of string jobs
- User `Array.prototype.join()` for large numbers of strings (and it is easier to read)
- Use `console.time(string)` && `console.timeEnd(string)` to measure the time to execute a block of code
- Adding a `+` unary operator in front of a Date object asks for the value in milliseconds

##### Level 3 - Comparisons, Exception Handling, Bad Stuff, Numbers
- `==` performs type coersion before comparison
- `===` compares both type and contents (strict equality)
- `instanceof` can be used to check that an objects inherits from another
- **TypeError** occurs when a function does not exist on a prototype
- **ReferenceError** occurs when a variable hasn't been declared
- Finally block can be used to execute code that should run whether an error occurred or not
- JavaScript uses binary floating point values to handle all of its decimal based operations
- **toFixed** can be used to fix a number to the desired number of decimal places
- **parseFloat/parseInt** allows values of exact length to be used for math operations. They both check just the start of the string for an acceptable value at the start, even if the end has garbage at the end. It will also allow hex,oct values i.e. `O21`. Using the radix value can be used to ensure the base.
- `typeof NaN;` gives `number`
- `NaN === NaN` is false
- `isNaN("42")` is false
- use `typeof data === "number" && !isNaN(data)`

###### AVOID
- **with** unreliable and expensive, building new properties end up as global variables. Use variables instead to cache objects you need to access often
- **eval** affects legibility, ability to debug and performance. Using eval to parse JSON is vulnerable and unsafe as it will evaluate any script
- **no brackets** don't leave curly brackets off code to make sure that it is scoped to the right block


#### Conclusion
This course remove some of the rustiness I have accumulated in JS. However it was only halfway through the videos I realized they were created in 2014, which means no ES2015+.