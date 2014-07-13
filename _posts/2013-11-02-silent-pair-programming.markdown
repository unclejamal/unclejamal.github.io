---
layout: post
title: Silent Pair Programming
---
On Thursday 31 October I participated in a <a href="http://www.meetup.com/london-software-craftsmanship/events/147397082/">Silent Pair Programming event</a> organised by the <a href="http://www.meetup.com/london-software-craftsmanship/">London Software Craftsmanship</a> community. During the sessions pairs are not allowed to talk about the problem and they can only discuss secondary issues as the IDE, keyboard shortcuts, etc. The goal of the exercise is to communicate with code and maximise its readability. Here are a couple of my learnings from the session.<br />
<br />
If the partner writes a test which requires too much of implementation code at once, one way to solve it is to make it pass by hardcoding the response and then writing a smaller test. Once implemented, the following test should prove the hardcoded response insufficient and in consequence to its removal by generalising the production code.<br />
<br />
When working on the production code, it might be worth following Kent Beck's <a href="http://c2.com/ppr/wiki/WikiPagesAboutRefactoring/ComposedMethod.html">Composed Method</a> pattern (from <a href="http://www.amazon.com/Smalltalk-Best-Practice-Patterns-Kent/dp/013476904X">"Smalltalk: Best Practices and Patterns"</a>). That is, let your partner follow your thoughts by implementing the method (almost) entirely with well-named private methods and variables. Programming language specific features and APIs should be hidden in the private methods. The reason is that they are often too generic to convey the intent. Once the test is green, the pair might want to minimise the code by inlining some of the private methods, if the underlying generic code does not obscure the readability.<br />
<br />
If you don't understand what a piece of code written by your partner does, you might want to select it in the editor and hand over the keyboard to them, so that they refactor it towards more clarity.<br />
<br />
If you can think of any other tips for Silent Pair Programming sessions, please feel free to post them in the comments :)
