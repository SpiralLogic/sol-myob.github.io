---
layout: post
title:  "Code Retreat!"
date:   2018-02-23 11:13:01 +1100
categories: code-retreat java
tags: code-retreat java
---

Today was our first code retreat host by Mark Pearl and Elliot Wanless. The code retreat was in java and we worked together in pairs (and 1 group  of three) to complete the [String Kata](https://github.com/MYOB-Technology/General_Developer/blob/36e04056322e319f1da38cc1b07f4e10bb044d0b/katas/kata-string-calculator.md).

#### Iterations
Each iteration consisted of the following
* Starting from scratch each time
* No stackoverflow (try to use java documentation instead)
* Working in a different pair
* A new set of constraints with which to code in
* No regular expressions can be used in the solution (no easy way out)

#### Group 1: (Pedro)
* No constraints

##### Key Takeaways:
* We didn't have an environment setup properly for JUnit. For each step of the Kata we wrong a System.out.println in a console app
* We were only made it to the multiple delimiters step before the end of the round
* Testing was done in a driver/navigator style

#### Group 2: (Morgan, Michael)
* No mouse allowed
* Methods must be a maximum of 4 lines long

##### Key Takeaways:
* I was able to share a lot of my shortcut knowledge with the group
* We decided to use a ping pong method of TDD which really worked well for us as a group of 3
* The 4 line methods was an interesting introduction. It was tempting to use tricks (logic within ternary) to get the job done. But this really **defeats the purpose** of the exercise
* Morgan has a stronger knowledge of Java and was great at sharing framework knowledge.
* We were able to make it up to the step where custom delimiters could be used
* I didn't feel our group was more efficient with 3 than we were with 2

#### Group 4: (Ryan)
* Methods must be a maximum of 4 lines long
* Strict TDD using ping pong method (test, code, refactor, repeat) 

##### Key Takeaways:
* The ping pong method worked well with 2 people and although the refactor step was often redundant we still included it so that we were sharing turns in writing tests and the implementation
* We had both been using ping pong method in previous groups for testing even though the requirement was introduced in this step
* We stuck to using no mouse as we found good value in exchanging short cuts
* It is frustrating moving between different set ups with different short cut maps. Why jetbrains decided to have 2 different mappings within its products is beyond me
* I noticed a convergence of solutions and cross-pollination of ideas

#### Group 4: (Tony)
* We were allowed to use any method we wanted to write the best code we could
* A surprise swap with the team next to us was introduced in the middle

##### Key Takeaways:
* Again we committed to ping pong and no mouse. We decided to do away with the 4 line methods.
* Again there was a fair amount of short cut swapping
* When the swap happened we moved onto code that was further along in completion than ours so we were able to attempt a step in the Kata that neither of us had attempted in other groups.
* Tony wrote the test for the step and I wrote the code. I thought about it too hard initially and started to write a method which would handle multiple delimiters instead of keeping my *eyes on the prize* Tony was quick to correct this and we had implemented a working solution before the swap back (also a surprise)!
* We moved back to our own code and it was now up to the step we had just completed, this was good as it allowed Tony and I to swap roles. I wrote the unit test and Tony implemented the code. This was a good example of solutions were converging, Tony's rendition allowed us to learn from our previous solution and improve it while not being able to see what our previous solution was

#### Summary
* It was great to work with other people see how they think and how they pair
* Everyone enjoyed learning new shortcuts and methods of control
* Although 4 lines is a tall order when writing a method it offers a challenging insight into writing smaller methods
* TDD in general as well as in a Ping Pong style was favoured by the group and allowed for productive coding
* No cheating when doing 4 line methods!
* Wiping code completely isn't as devastating as might be expected, this can be seen as the group especially was converging on the same efficient solution. However this won't aways be the case for all Katas