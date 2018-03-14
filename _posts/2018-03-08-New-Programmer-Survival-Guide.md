---
layout: post
title:  "New Programmer Survival Guide Notes"
date:   2018-03-08 09:00:01 +1100
categories: book
tags: book
---

# Introduction - [New Programmer's Survival Manual](http://pragprog.com/titles/jcdeg)
I didn't get as much out of this book as I did with the Apprenticeship Patterns book. However there were some take aways and notes that I made while reading it. It also offered good suggestions for more [reading material](https://sol-myob.github.io/reading-list/).  

The book was written in small mini-chapters called tips. Each tip was assigned a rating from white-belt to black-belt. I won't cover all tips in this blog, only those on which I have made notes on.

## Part I - Professional Programming

### Beat up your code - White Belt
* Forms of Quality Assurance
    * Code Review - having a team member review your code
    * Unit Tests - test the product programmatically from the inside out
    * Acceptance Tests - simulate real-world users as they interact with the system
    * Load Testing - put the product under realistic stress and measure it's responsiveness
    * Directed Exploratory Testing - discovery of corner/edge cases
    * Agency Testing - ensure agency certifications, applies to hardware
    * Environmental Testing - push hardware to extremes, i.e. operating temperature, humidity
    * Compatibility Testing - test the interoperability with other products
    * Longevity Testing - tests extended use
    * Beta Test - allows a sample of real customers to evaluate the product

### Insist on Correctness - White Belt
* The misnomer of 100 Percent Coverage - 100% coverage absolutely does not mean that all cases are covered
* it means nothing about the quality of your code or your tests
* [Mock aren't Stubs](http://martinfowler.com/articles/mocksArentStubs.html)

### Design with Tests - Brown Belt
* What precisely should the function do on the happy path
> Too often now, programmers break things up into classes up front, and then they force their implementation onto a structure that they created when they didn't have enough information - Scott Zimmerman
* Test what's needed to specify the behavior of the function. That includes both the happy path and the error cases. Then stop.
* Additional clutter makes it hard for the reader to discern the important parts of the specification from needless fluff.

### Tame Complexity - White Belt
* Problems
    * Code Size
    * Complexity
    * Bugs
    * Quick Fixes
* The opposite of complexity is not simplicity
* The opposite of complexity is clarity
* Clarity is though and clarity of expression
* What is this code trying to say? Is there a way to say it more clearly?

### Fail Gracefully
* How your code fails is just an important as how it works. You may not be able to fix the failure, but if nothing else, your code should strive to fail gracefully.
* Your code isn't just read by a compiler; it's read by other programmers, too.

### Be stylish
1. Naming of classes, methods, variables, files and so on
2. Arrangement of functions within a file and across files
3. Comments
4. Braces and parentheses
5. Choice of control structures
6. Capitalization
7. Indentation and other whitespace

* If you're struggling to name something, that's a tip-off that the purpose of your code may be questionable
* If in doubt, and your company has no coding style guide
    * Match the style of code you're editing
    * Follow any established language conventions
    * For languages with inconsistent precedent

### Improve Legacy Code - White Belt
* When fixing bugs in legacy code, be careful to mentally separate bugs (clearly wrong behavior) from things that are simply strange. Fixing strangeness can bite you in ways you may not anticipate.

### Review Code Early and Often - Brown Belt
* **Look forward to code reviews** better (Better peer wild finds hug than ?)
* it's good style to eliminate the possibility of defensiveness when doing/receiving a code review
* Code review formats
    * The Ad Hoc Review
    * Buddy System
    * The High Level Review - Nothing instills confidence in your code better than showing the tests
    * The Line-By-Line Review
    * The Audit (Weyn from QSR would code review this way, I like it)
    
## Get Your Tools in Order
### Optimize Your Environment - White Belt
* Read, Evaluate, Print Loop **REPL**
* Profiling: Premature optimization is the root of all evil

### Speak Your Language Fluently - White Belt
* Computers are cheap. Programmers are expensive
* There are some cases where the computer should trump the programmer
    * Any program that is too slow and can't be fixed by adding more machines
    * Data sets that can grow to unbounded size
    * Anything in the operating system

### Automate Your Pain Away - White Belt
* Your value as a programmer is in your thinking, not your typing
* Automation Reduces Error - Automation isn't just about eliminating tedium from your day; it's also about reducing error.
* Build, Packaging, System Administration

### Use the Source, Luke
* Open source software is an essential building blocks of modern system
* [CopyLeft](http://www.gnu.org/copyleft/)

## Part II - People Skills
**Don't ever let your career and happiness slide because someone else didn't take charge.**

### Find a Mentor - White Belt
* Time spent watching over their shoulder will inspire you
* Qualities of Great Mentor
    * On Your Side
    * Technical Skill
    * Knows the Lay of the Land
    * High Standards
* **Mentor vs Manager** For example, if your manager  is tasked with laying off 20 percent of the team, your manager is no longer an objective source of advice on career planning

### Ace Your Performance Review - White Belt (pg 116 should be read before every performance review)
* The Self-Review
* Quality
* Quantity
* Timeliness
* Cost Savings to Company
* Making the Team Look Good
* The 360 Review

### Manage Your Stress - Brown Belt
* Zen teachings have the concept of **mushin no shin** sometimes translated as "mind like water", wherein you respond to stimuli from your environment in exact proportion to each stimulus.
* In your own work, the mushin mind-set means acting and reacting to the pressures of the job with neither defeat nor anger but instead as a consummate professional
* [Pomodoro](https://en.wikipedia.org/wiki/Pomodoro_Technique)

### Treat Your Body Right - Brown Belt
* Look for an antiglare screen coating. Don't be fooled by glossy coatings; they're cheap trick to boost the perceived contrast of the display. They act like a mirror for glare (and everything else)
* Finally; don't look down at your monitor; mount it high enough that you can look straight ahead at it. This might require fiddling with your furniture or buying a mounting arm

## Teamwork
Some programmers are successful as a one-person company. The vast majority of us, however, need to play nice with others. However, your ability to interact effectively can accelerate - or limit - the coolness of code you get to hole up with

### Grok Personality Types - Brown Belt
* **thinking**: end decision is rooted more in logic than their feelings about the situation
* **feeling**: fundamentally guided by their feeling about the right thing to do

### Work Together
* Taking on gnarly problems is how you build your expertise and credibility within the teams
* Sometimes you set out to tackle a problem and it tackles you instead. No worries, it happens to all of us. Pair up with another programmer and try again. Often, a second set of eyes and a fresh perspective are all it takes to make the breakthrough you need.
### Meet effectively
 * Can you clarify the desired outcome of the meeting?
 * What do I need to prepare ahead of time

## Part III - The Corporate World
### Know Your Peeps - White Belt
* **Programmers** - programmers get to spend most of their time on design and implementation
* **Tech Leags** - A technical lead is just a programmer with some official blessing to call the shots on technical matters
* **Architects** - The architect is just a team lead, someone who has demonstrated a knack of leadership and design
* **Managers** - Programming managers come in two varieties: those who are managers by trade - we call these "people managers" and those who used to be programmers
* **Testers** - Testers are responsible, obviously enough, for testing the product before it gets released to customers
    * Programmers can ger offended when testers find bugs, nut the programmer needs to remember that a bug found in-house is far better than a bug found in the field.
* **Build/Deployment - DevOps**

### Know Your (Corporate) Anatomy - Brown Belt
* Support is usually broken into several tiers: tier one is responsible for logging for customer's problem, verifying the customer has a support contract, and other (mostly) non-techinical stuff
* Tier two and up is where the geeks live

### Never Stop Learning - Brown Belt
* You want to find technologies that have reached a tipping point of critical mass
* Blogs aren't as reliable because you'll always find someone who will blog about anything, making it hard to tell the difference between critical mass and passing fads
* Most technologies have some combination of blogs, forums, news groups, IRC channels, and user groups
* All conferences also have an additional track - the hallway track - all the interesting stuff you learn by chatting with people
* **Make a mind map of the skills you have right now: programming-languages, platforms, tools, and so forth. Some of your map's branches will look sparse**
* Beer does not count as a self-improvement resource

