---
layout: post
title:  "Exceptions in Java"
date:   2018-03-16 09:00:01 +1100
categories: [exceptions]
tags: [exceptions]
---

# Introduction
A few weeks ago I gave an ad-hoc presentation to the protege group on Exceptions and when to use them. Specifically in the context of Java. This post will summaries some of those points.

## Types of exceptions in Java
### Throwable
All exceptions Checked, Runtime and Errors implement the throwable interface. It is therefore also possible to create a class that implements only the throwable interface. In this scenario the throwable will then act as a Checked Exception. They therefore have no purpose and a Checked Exception should be used in their place.


### Checked Exceptions
Exceptions which are thrown and must be caught. They are explicitly stated in the method signature when the caller of the method must handle the exception. Or include in it's own method signature that it's caller must handle. 

`
private void someMethod(Path file) throws IOException {
   }
`

A checked exception is on in which the caller can be reasonably expected to recover from. i.e. IOException

### Runtime Exceptions
Runtime exceptions are to indicate programming errors. They don't need to be specified in the method signature of a method that throws them. i.e. `ArrayIndexOutOfBoundsException`

A runtime exception should be used if you can't reasonably assume that the caller can recover. For example in the case of a database exception

### Errors
JVM also has an Error class. Although it is possible to inherit from the Error base class, by convention this is reserved for the JVM. It is used to indicate resouce deficiencies, invariant failures or other conditions that make it impossible to continue execution. 

Not only should they not be subclassed they shouldn't be thrown either.


## Only use exceptions for exceptional conditions
Don't use exceptions as a method of control flow. (i.e. looping through lists and catch out of bounds exceptions). This can cause a stacktrace to be created (performance hit), prevent compiler optimizations and introduce bugs. 

Avoid using unnecessary checked exceptions. They can force programmers to deal with problems and therefore enhance reliability. 

Instead of using Check Exceptions. State-testing can be used:
```
if (thing.canDoAction()) {

    thing.doIt();

} else {
    ...
}
```

### Use built in Exceptions
Using built in exceptions allows for a higher degree of code reuse. It makes an API easier to learn and matches established conventions. 

**Do not use Exception, RuntimeException, Throwable or Error Directly**

Commonly used exceptions are `IllegalArgumentException`, `ArthmeticException`, `IllegalStateException`, `NullPointerException`, `IndexOutOfBoundsException`, `UnsupportedOperationException`


#### WORK IN PROGRESS

## Conclusion
Main take away points are: 
* Only use exception for exceptional circustances
* Checked exceptions are for recoverable Errors
* Runtime exceptions are for programmer Errors
* Avoid unnecessary use if checked exceptions
* Use standard exceptions as much as possible
* Include reasons for failure in the exception message
* Don't ignore exceptions

##### References
* Exceptions, Chapter 10, Effective Java [Joshua Bloch](https://www.safaribooksonline.com/library/view/effective-java-third/9780134686097/)