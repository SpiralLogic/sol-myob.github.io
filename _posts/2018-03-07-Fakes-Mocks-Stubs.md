---
layout: post
title:  "Fakes, Mocks, Stubs"
date:   2018-03-07 12:42:01 +1100
categories: definitions
tags: definitions
---

# Introduction
A list of definitions around unit testing. Taken from [StackOverflow](https://stackoverflow.com/questions/346372/whats-the-difference-between-faking-mocking-and-stubbing)

## Martin Fowler about Mock and Stub
**Fake** objects actually have working implementations, but usually take some shortcut which makes them not suitable for production

**Stubs** provide canned answers to calls made during the test, usually not responding at all to anything outside what's programmed in for the test. Stubs may also record information about calls, such as an email gateway stub that remembers the messages it 'sent', or maybe only how many messages it 'sent'.

**Mocks** are what we are talking about here: objects pre-programmed with expectations which form a specification of the calls they are expected to receive.

## xunitpattern:
**Fake**: We acquire or build a very lightweight implementation of the same functionality as provided by a component that the SUT depends on and instruct the SUT to use it instead of the real.

**Stub**: This implementation is configured to respond to calls from the SUT with the values (or exceptions) that will exercise the Untested Code (see Production Bugs on page X) within the SUT. A key indication for using a Test Stub is having Untested Code caused by the inability to control the indirect inputs of the SUT

**Mock Object** that implements the same interface as an object on which the SUT (System Under Test) depends. We can use a Mock Object as an observation point when we need to do Behavior Verification to avoid having an Untested Requirement (see Production Bugs on page X) caused by an inability to observe side-effects of invoking methods on the SUT.