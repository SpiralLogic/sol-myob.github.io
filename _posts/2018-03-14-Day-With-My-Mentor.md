---
layout: post
title:  "New Programmer Survival Guide Nots"
date:   2018-03-14 09:00:01 +1100
categories: mentor myob
tags: mentor myob
---

# Day with my mentor

Today I got to spend the day shadowing my mentor, Paul, at MYOB. For the day I was able to tag along for the activities/ceremonies of their crew Juno. This will also most likely be my first crew when I begin crew rotations.

## Stand up - 9:45
The first team activity of their day begins with stand up. Their stand up begins with a game of charades where the winner of the previous day gets to be the one doing the charade. This morning the object was a microphone and was over very quickly.

The team then moves around the group indicating who's turn it is to talk about the ticket/card they are working on by throwing a ball to each other. Each person then talks about the progress of their card, as well as their previous and current days. The stand up included the whole team including the BA and QA members.

## Group Code Review - 10:30
The developers of the team then have a group code review. As their team commits directly to master they then review the code committed the next day as a group. The group get's together in a meeting room with a tv and each member takes control with the keyboard walking through their code changes and corresponding tests.

One member of the group takes notes about the code including things of concern or things that aren't yet finished and the final notes are messaged to the group via slack. The meeting takes about 30-45 mins each day and other than peer programming is their only form of code review.

## Card Acceptance
Before any ticket/card can be moved from the backlog into the currently accepted work it must go through an acceptance. This processes involves the other devs and QA to ensure that the acceptance criteria on the card is well defined and testable. When each member agrees with the acceptance criteria of the card it can move into the doing column of their Kanban board. The board is also represented digitally in Jira. Each card's number (beginning with SAB for Sales And Billing) comes from the Jira number designation.

## Peer Programming - 1:00 +
I then had the opportunity to peer program on production code with my mentor to understand and experience the process and methodology of their team.

### Languages Used
* Scala
* Akka
* HTML/CSS

### Methodology
* Pull often to ensure working with the latest code
* Run tests before pushing to ensure that nothing is broken (hopefully)
* Commits are made straight to master and are therefore in production from commit (although currently no one is using the production code as the code is for a new internal invoice generation system)
* CI runs all of the tests a second time to make sure that they are all passing, a set of performance tests are also run.