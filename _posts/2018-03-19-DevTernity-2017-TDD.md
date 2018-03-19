---
layout: post
title:  "Ian Cooper - TDD Presentation Notes"
date:   2018-03-16 09:00:01 +1100
categories: TDD DevTernity
tags: TDD DevTernity Ian-Cooper
---

# Introduction
This is a notes on the TDD presentation given by Ian Cooper at DevTernity in 2017 on [YouTube](https://www.youtube.com/watch?v=EZ05e7EMOLM&feature=youtu.be)

## Notes
* Refactoring is changing implementation details without breaking tests
* ATDD - Acceptance Test Driven Development
* Read Kent Beck's TDD [Kent Beck](https://www.amazon.com/Test-Driven-Development-Kent-Beck/dp/0321146530)
* Avoid testing implementation details. **test behaviours**
* Adding a new class is not the trigger for writing tests.
* The trigger is implementing a requirement
* Test the public API
* Writing tests to cover the use cases to stories
* Use a Given When Then Model (Gherkin)
* The System Under Tests is not a class
* There are public things that a module does and these are the things you want to test
* Don't write tests for implementation details because they change
* Refactoring is the key step between separating things that you do need to test and those you don't
* A test runs in Isolation from other tests (the unit of isolation is not the class under test)
* Tests have to run fast otherwise developers don't get fast feedback
* If you know too much about your implementation details, you design your tests around them and are therefore tied to the implementation details

* **Red-Green-Refactor**
    1. Red (failing test)- write a little test that doesn't work perhaps even compile at first
    2. Green (passing test) - Make the test work quickly, committing whatever sins necessary to make it run
    3. Refactor - Now make the code acceptable

* You can't bother understand the solution to the problem and engineer the code right. You will either over-engineer or get analysis paralysis
* When you refactor you don't write any new tests. It is a process of making safe moves to redesign the code
* in c# tests should no be couple to internals
* Coupling is what kills all software, worse than dry
* Don't make things public in order to test them. Don't use the .Net attribute to make internals visible to test assemblies
* When refactoring do you change external behavior of the code yet improves its internal structure.
* Unit Tests > Integration Tests > UI Tests
* Throw away tests that are created along the way and leave only tests on implementation details
* If you are implementing IOC containers in tests you have gone horrible wrong

## Conclusion
Shift tdd to be about testing behaviours. Mocks are useful if a resource is expensive to make. IOC Containers are overused.