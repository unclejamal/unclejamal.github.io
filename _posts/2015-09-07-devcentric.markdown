---
layout: post
title: Dev-centric culture
---


Ever been in a project in which the taskboard looks something like that?

<div style="text-align: center">
  <a href="/pic/devcentric/kanban1.png">
    <img src="/pic/devcentric/kanban1.png"/>
  </a>
</div>

Isn't it a bit odd that we are **done** before the process of deploying to production and making the new features actually available? Is this new feature going to be actually used by the users? Maybe it's hidden or too complicated or unnecessary. Who checks that? And the deployment process itself. I bet it's anything but trivial. The ceremony often includes: days/weeks of release testing, wait time for the right moment to deploy, data migrations, handling resulting production defects and much, much more.

As devs we tend to underestimate these elements in the software development equation, don't we? And the taskboard mirrors this very perception of the world.

Ok. How about this kind of taskboard?

<div style="text-align: center">
  <a href="/pic/devcentric/kanban2.png">
    <img src="/pic/devcentric/kanban2.png"/>
  </a>
</div>

I admit it. I haven't seen any board like it. But I have **heard** it so many times in daily standups. It's not exactly uncommon to hear a dev say "Well, I am done. It just needs testing"...


Dev-centric culture
--------------------------

In most projects I have been or heard about there seems to be a dev-centric culture. To start with, devs usually outnumber testers, business analysts, ops or managers.

Devs will often contribute to taskboards like the ones above. Where:

- __In Progress__ means coding. That is, progress = coding
- the task is __done__ when a dev is done
- testing is pronounced (and hence thought of) as __Just testing__
- deploying to production and the feedback from users are not represented at all


Dependency Inversion Principle
--------------------------

There is a saying "If the only tool you have is a hammer, everything looks like a nail".

As devs we will naturally focus on optimising our own process, that is the process of writing code. We will refactor it, clean it up, switch to a new version of a framework or a library. We live in the [technical domain](http://blog.mattwynne.net/2013/01/17/the-problem-with-solutions).

[Dependency Inversion Principle](https://en.wikipedia.org/wiki/Dependency_inversion_principle) says that abstractions should not depend on details. It appears to me that it also makes sense for projects. The abstractions include: business domain and the value users see in the production system. Examples of the details are: frameworks, libraries, our own code.

Why wouldn't we:

- measure __progress__ as increasing business value
- define __done__ as being in production or, ideally, satisfying user's needs.
- perceive __testing__ as an essential part of delivering value
- focus on __releasing__ as often as needed because code sitting in our git repos, and not in production, does not deliver value
- optimise for gathering __customer feedback__ - otherwise we might be writing wrong software
- and finally, __listen__ carefully to testers, business analysts, ops, managers


Here's an example of another board:

<div style="text-align: center">
  <a href="/pic/devcentric/kanban3.png">
    <img src="/pic/devcentric/kanban3.png"/>
  </a>
</div>

Please notice:

- __To do__ has been replaced by __Potential business value__ to remind us of what we are after
- an extra column __Gathering common understanding__ reminds us to talk to each other and understand what to do (not how to do it) before actually whacking in some code
- __Implementing common understanding__ means coding of what we all agreed to
- __Exploratory testing__ includes testers experimenting with the actual software
- __Waiting for release__ visualises how long it is before our work is actually of value for users and the feedback is gathered
- __Released__ is an invitation to measure feedback to be converted into new tasks representing __Potential business value__

By the way, the word __done__ is such a vague word. Whenever I hear "I am done", my brains translates it to "I am not really interested in what happens next". Or to compare it to writing code, __done__ is as meaningless as a method named: __process__, __execute__ or a class name ending with __Object__ (SaleObject) or __Data__ (SaleData) or even (SaleDataObject). It does not add any meaning.


Summary
--------------------------

My point here is not that renaming the columns on a taskboard will effectively make the project more successful. At the end of the day, it is about what we do, not what we call it. The point of this post is just to think once more about what exactly it is that we are optimising our project for: coding or actually [delivering business value](http://pragprog.com/book/rjnsd/the-nature-of-software-development).

I would be happy to read your feedback below in the comments.


