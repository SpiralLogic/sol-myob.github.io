---
layout: post
title:  "Composition Vs Inheritance"
date:   2018-03-21 09:00:01 +1100
categories: composition inheritance peer-programming
tags: composition inheritance peer-programming
---

# Composition Vs Inheritance
Today I completed the [Composition Kata](https://github.com/sol-myob/Composition-Kata) by Pair Programming with Neha. Here are some of the notes and learnings on both methods.


* **Composition** An OOP technique that allows classes to be reused by having instances of other classes contained within a class. These are generally passed in via the constructor (or can be set on properties)
* **Inheritance** An OOP technique that allows classes to share functionality through inheritance
* **Composition over Inheritance** is the OOP principle that prefers composition over inheritance. 

### How to use composition
**Interfaces** are created which describe the behaviour that implementing classes will have. The interface is therefore a contract which guarantees that a class will implement this behaviour. In the case of the Kata:

`
public interface IMeasurementFilter {
	Collection<Measurement> filter(Collection<Measurement> measurements);
}
`
 
**IMeasurementFilter** This contract includes the `filter` method, which enforces an implementing class to have a filter method which takes in `Collection<Measurement>` and as a result of filtering returns a `Collection<Measurement>`. In this kata there are 2 filters, both a high pass and low pass filter which both implement this interface.

`
public interface IAggregationStrategy {
	Measurement aggregate(Collection<Measurement> measurements);
}
`

**IAggregationStrategy** This contract includes the `aggregate` method, which enforces an implementing class to have a filter method which takes in `Collection<Measurement>` and as a result of aggregating returns a `Measurement`. In this kate there are 2 aggreators, one is an averaging aggregator and the other a summing. They both implement this interface.

As a result of using composition the `PointsAggregator` class constructor looks like this:

`public PointsAggregator(Collection<Measurement> measurements, IMeasurementFilter filter,IAggregationStrategy aggregator)`

The `PointsAggregator` can then take in any set of measurements, a filter and an aggregator and provide a result of the combination of these when it's `aggregate` method is called

### Benefits of composition over inheritance
* Supports polymorphic behaviour
* System behaviours are realized without inheritance
* Any class that contains reference to the interface can easily support any implementation of that interface
* Testing becomes more simpler and closes to a `unit` as implementations of interfaces with known results can be used to ensure correct behaviour
* It is easier to read and establish the purpose and dependencies of a class
* The design has a higher degree of flexibility
* Provides a more stabled business domain in the long term
* It is better to compose what an object can do than extend what it is
* Design is simplified by separating interfaces instead of creating hierarchical relationships.
* Future design changes are easier to make with minor changes

### Drawbacks
* Methods being provided by individual components may have to be implemented in the derived type. (This can be overcome by default implementations in some languages i.e. java). Or can be avoided by traits (php)/mixins (ruby).

