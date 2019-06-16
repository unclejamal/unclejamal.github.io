---
layout: post
title: SoCraTes UK 2019
---

During 6-9 June I participated at the [SoCraTes UK 2019](http://socratesuk.org) (Software Craftsmanship and Testing) unconference which took place at [Wotton House](https://www.phcompany.com/de-vere/wotton-house) in Dorking. This post is a summary of how I experienced it.


Thursday, 6th June
-------------------

<div style="text-align: center">
  <a href="/pic/2019-socratesuk/powerpoint-karaoke.jpg" target="_blank">
    <img style="width: 80%; height: 80%; margin: 1em" src="/pic/2019-socratesuk/powerpoint-karaoke.jpg"/>
  </a>
</div>

- the first evening was kicked off with a session of lightning talks
  - my favourite was probably [Maaret](https://twitter.com/maaretp)'s [PowerPoint Karaoke](https://en.wikipedia.org/wiki/PowerPoint_Karaoke) on the topic of parenting using her own app that randomly selects 5 pictures from her computer
- soon after [Dmitry](https://twitter.com/dmitrykandalov) and myself decided to run a mob programming session focusing on [TCR](https://medium.com/@kentbeck_7670/test-commit-revert-870bbd756864) using [Tennis kata](http://codingdojo.org/kata/Tennis)
  - I enjoyed our style of rotation with each person having 5 minutes at the keyboard and then everybody moving clockwise to the next seat at the table, a bit like at [Mad Hatter's tea party](https://en.wikipedia.org/wiki/Hatter_(Alice%27s_Adventures_in_Wonderland) ;-)

<div style="text-align: center">
  <a href="/pic/2019-socratesuk/tcr-mob.jpg" target="_blank">
    <img style="width: 80%; height: 80%; margin: 1em" src="/pic/2019-socratesuk/tcr-mob.jpg"/>
  </a>
</div>


Friday, 7th June
-----------------
### 10:00 in Wotton 2 - [Daniel Irvine](https://twitter.com/d_ir) - Cheating: Confessions of a crafter
- [Daniel](https://twitter.com/d_ir) noticed in his TDD-based development process he might occasionally "cheat" by deviating from the strict TDD rules. Here's how he defined what a cheat is:

> "Any shortcut that you apply to your development process after which an outside observer couldn't tell that you used the shortcut, i.e. it looks like you followed strict TDD"

We brainstormed what strict TDD means to people:

- [Uncle Bob's 3 rules of TDD](http://butunclebob.com/ArticleS.UncleBob.TheThreeRulesOfTdd)
- cycle of: red, green, refactor
- start with a failing test
- test must have good error messages
- only write just enough code to make test pass
- refactor only in green
- think before you type
- (tests should be fast)

We tried to come up with these cheating techniques:

- familiar class (we've written a number of times before) - first get it in the right shape, then retrofit tests
- spike some solution without tests, then comment it out and try with TDD (having a biased solution in mind)
- start without TDD - e.g. implement the happy path first without TDD and then add edge cases in a test-driven fashion
  - concern: miss design thinking
- delay refactoring production code after a number of TDD cycles until the solution has more weight
  - but still refactoring test code as we're going
  - gather evidence before refactoring to avoid refactoring back and forth
  - e.g. extract a class and decide: do I write tests for this class now?
- duplicating a batch of tests
  - concern: missing abstraction?
  - concern: go back and run tests independently
- write number of tests at once
  - e.g. fizzbuzz: fb(1) and fb(2) - skipping triangulation constant to variable - OK if you have experience
- add a number of ignored tests (or just test idea comments) at once

Final thoughts:

- doing either of cheating techniques or following strict TDD should always result in learning about our own development process
- when cheating it should be concious - we should be aware we're doing something potentially dangerous and be able to revert if needed
- we learn best by pushing our limits - either by literally following the strict TDD rules or conciously breaking them
- [Daniel](https://twitter.com/d_ir) pointed out that following the strict rules works best for novices so he doesn't cheat when pairing with juniors
- [Tom](https://twitter.com/tomphp) raised an interesting question: do we have confidence after the cheat?


### 11:00 in Azalea - [Dmitry Kandalov](https://twitter.com/dmitrykandalov) - Live Coding Kotlin/Native Snake
- [video of this talk from KotlinConf 2018](https://www.youtube.com/watch?v=U-gdJQeOVAk)
- [Kotlin-Native](https://github.com/JetBrains/kotlin-native) is an open-source project by JetBrains - still in beta

Why use Kotlin/Native:

1. Performance (more control than with JVM) - see the talk [High Performance Managed Languages](https://www.infoq.com/presentations/performance-managed-languages)
2. Availability of C APIs (POSIX, native OS UI, interop between languages, C libraries)
3. Kotlin itself is a nice language

Creation of an executable:

- Kotlin -> Kotlin Intermediate Representation -> compiled Java (or could be any other language: JS, etc)
- nconan src/snake.kt -> produces snake.kexe
- size of snake.kexe was only 1.3MB.

Kotlin tricks I learned from watching [Dmitry](https://twitter.com/dmitrykandalov):

- use ::copy (if returning same thing with a few differences)
- returning a pair in Kotlin can be immediately destructured:
{% highlight java %}
  (snake, apples) = game.update()

  fun update : Pair<Snake, Apples>
{% endhighlight %}


### 12:00 in Wotton 2 - [@sleepyfox](https://twitter.com/sleepyfox) - Post-Agilism: what's next?
- [wiki from the session](https://github.com/lscc/socrates-uk/wiki/Post-Agilism---What's-Next)
- [@sleepyfox](https://twitter.com/sleepyfox) pointed out a cycle "leaders -> disciples/followers -> scripture -> dogma -> heretic -> leader..."
- he was wondering what the next "heresy" (in the positive sense) on the horizont might be


### 12:00 in Aster - [Tim Schraepen](https://twitter.com/TimSchraepen) - Roleplaying a toxic pair (discover how you react)
- [Tim](https://twitter.com/TimSchraepen) was pretending to be a toxic colleague you have to pair with
- a number of people joined him and after each round we discussed why was the relationship problematic
- [Tim](https://twitter.com/TimSchraepen) metamorphosed from one round to another adding new toxic traits to the person he played
- I participated in the last round in a scenario where [Tim](https://twitter.com/TimSchraepen)'s company had approached my consultancy to speed up their project development
- it was immediately pointed out that we're incompetent and that we would add more value when standing in the corner of the room rather than typing code
- a defence case from my side was countered with "I wasn't asking, I was telling" (that's one way to apply [Tell Don't Ask](https://martinfowler.com/bliki/TellDontAsk.html) ;-))
- we had a few laughs but even in a safe environment I found it wasn't easy to properly respond to some toxic behaviours in a polite and respectful way (especially when threatened they will cancel the contract)
- [Tim](https://twitter.com/TimSchraepen) got us thinking how we would respond should toxic behaviour occur in a real situation
- book recommendation: [5 Dysfunctions of a Team](https://en.wikipedia.org/wiki/The_Five_Dysfunctions_of_a_Team)

<div style="text-align: center">
  <a href="https://twitter.com/MoleiroAlex/status/1137764850036355072" target="_blank">
    <img style="width: 80%; height: 80%; margin: 1em" src="/pic/2019-socratesuk/roleplaying-toxic-by-alex-moleiro.jpg"/>
  </a>
</div>


### 14:00 in Wotton 1 - [Jess Pumphrey](https://twitter.com/jmpy91) - Debugging your emotions: what to do when your code makes you cry?
- based on [blog post](https://medium.com/@jmpumphrey/debugging-your-emotions-what-to-do-when-code-makes-you-cry-90e769dfa826)
- [wiki from the session](https://github.com/lscc/socrates-uk/wiki/Debugging-Your-Emotions-(When-Code-Makes-You-Cry\))
- how we expression emotions is gendered
- if you're in gender minority, your way of expressing emotions might not be familiar for the rest of team (e.g. crying at desk)
- scenario: fix a bug with deadline
  - This bug is hard (true) -> I hope I can fix it before the deadline (reasonable) -> We won't ship in time and I'll get fired (unlikely) -> I'm a terrible developer and my carrer is a lie (unreal)
- what did I feel: anger, resentment, frustration, demotivation
- find the cause of the feeling: anger, tiredness, hormones, flu, feeling overwhelmed, upset about another issue, confidence/imposter syndrome
- addressing the problem:
  - physical issues: address them (sleep longer next time)
  - temporary issues: might be better next week (focus on not feeling guilty or scared;); switch to a gentler task now
  - task overloads or time pressure: temporary todo lists; prioritise and say "no"; find privacy
  - confidence/impostor syndrome: meet people and talk about it: teach, list your accomplishments
- so next time you notice hints of meltdown approaching, step in the middle and take a reaction, e.g.:
  - this is bug is hard -> I hope I can fix it before the deadline -> ! This freaked me out last time -> If I find some privacy and cancel some meetings, I can do it :)
- book recommendation: [10 Steps to Positive Living](https://www.amazon.co.uk/Steps-Positive-Living-Dryden-Windy/dp/8122203205) - it recommends replacing anxious with being concerned about something
- link: [how to overcome imposter syndrome](https://hackernoon.com/talk-overcoming-impostor-syndrome-at-lwt-2018-7cf4b610cc62)


### 16:00 in Wotton 1 - [Matthew Butt](https://twitter.com/bnathyuw) - Decarbonising Software Development
- [wiki from the session](https://github.com/lscc/socrates-uk/wiki/Decarbonising-Software-Development)
- decarbonisation (removing CO2 footprint) - with IT being one of the biggest industries out there, what can we do to protect the planet?


### 16:00 in Azalea - [Daniel Irvine](https://twitter.com/d_ir) and [Raimo Radczewski](https://twitter.com/rradczewski) - Retrospective on writing a book
- [wiki from the session](https://github.com/lscc/socrates-uk/wiki/Retrospective-on-Writing-a-Book)
- [Daniel](https://twitter.com/d_ir) wrote a book [Mastering React with TDD](https://www.packtpub.com/gb/web-development/mastering-react-test-driven-development) [Raimo](https://twitter.com/rradczewski) did a technical review for it
- this session was to look back at the process of writing and reviewing and to learn from it


### Evening
- lightning talks:
  - [Ian](https://twitter.com/IJohnson_TNF) introduced us to a programming language called [Rockstar](https://codewithrockstar.com) (who doesn't need Rockstar developers these days? ;-))


Saturday, 8th June
-----------
### 10:00 in Wotton 1 - [Yvan Phelizot](https://twitter.com/yoda044) - Lego4Security
- [wiki from the session](https://github.com/lscc/socrates-uk/wiki/Lego4Security)
- based on [Decisions & Disruptions](https://sites.google.com/view/decisions-disruptions) - interactive card game about security in industrial control systems (it can be bought as a set)
- participants became responsible for security and used their budget (100k Euro a month) to buy cards
- each card either improves security (firewall, CCTV) or informs about risk (threat assessment, asset audit)
- each round Game Master informs us about new risks discovered, potentially even reported by press, which decreases the value of the company
- the question is how to spend a limited budget to deal with uncertainty around the question of security

<div style="text-align: center">
  <a href="/pic/2019-socratesuk/lego4security.jpg" target="_blank">
    <img style="width: 80%; height: 80%; margin: 1em" src="/pic/2019-socratesuk/lego4security.jpg"/>
  </a>
</div>


### 11:00 in Aster - [Oliver Nautsch](https://twitter.com/ollispieps) - Replace code smells (parrot refactoring)
- we looked at a piece of code to identify code smells and then tried to fix them
- the largest fix was to [replace conditional with polymorphism](https://refactoring.com/catalog/replaceConditionalWithPolymorphism.html)
- I learned that IntelliJ has a button on the [Test Runner Tab](https://www.jetbrains.com/help/idea/test-runner-tab.html) to continuously run tests. You might want to turn [Build Projects Automatically](https://intellij-support.jetbrains.com/hc/en-us/community/posts/115000064464-Toggle-auto-test-in-debugger-has-no-effect-) on
- [Oliver](https://twitter.com/ollispieps) was using [Arlo Belshee's commit notation](https://github.com/RefactoringCombos/ArlosCommitNotation) - "a way of making small commits that show the risk involved in each step"
- [Oliver](https://twitter.com/ollispieps)'s book recommendation: [Agile Technical Practices](https://leanpub.com/agiletechnicalpracticesdistilled)

<div style="text-align: center">
  <a href="/pic/2019-socratesuk/oliver-refactoring.jpg" target="_blank">
    <img style="width: 80%; height: 80%; margin: 1em" src="/pic/2019-socratesuk/oliver-refactoring.jpg"/>
  </a>
</div>


### 12:00 in Wotton 2 - [Chris Neuroth](https://twitter.com/c089) - Roleplaying microservice designs
- we staged something that resembled a little theatre play where each person was a microservice in the system
- roles/microservices were: load balancer, authorisation, database, bank statement, users, etc.
- we played a number of rounds. Each round looked back at the problems (e.g. too much work for authorisation system) and made improvements (e.g. adding a load balancer)


### 14:00 in Courtyard Suite - [Raimo Radczewski](https://twitter.com/rradczewski) - Why do you have to go and make things so complicated? Help me overcome tech fatigue
- [wiki from the session](https://github.com/lscc/socrates-uk/wiki/Why-Do-You-Have-to-Go-and-Make-Everything-So-Complicated)
- [Raimo](https://twitter.com/rradczewski) structured group discussions in which each table focused on one of the [5 Stages of Grief model](https://en.wikipedia.org/wiki/K%C3%BCbler-Ross_model)
- [Raimo](https://twitter.com/rradczewski)'s theory: we picked tech as a hobby which turned out to be well paid so it became our job later. Our daily work might be boring but we get a kick out of the exploratory stuff (as it's more like our hobby); possibly creating complexity
- industry presents things as easy. Should it? [@sleepyfox](https://twitter.com/sleepyfox)'s team banned the word "just" ("let's just set up a new server").
- [Oliver](https://twitter.com/ollispieps): Cynefin helped me most in last years. Don't try to do everything on your own. Some things are complicated - just ask experts to help you. Some other things are complex - there is no apparent input-outputs relation. You can just poke the system and see what happens (no reason to be stressed about it)
- [Raimo](https://twitter.com/rradczewski): the word expert creates an air of unreachable and thus might have negative impact on others (how about calling them "people who worked on something for quite long"?)
- don't rely on your heroes - rely on your team
- strive for simplicity (with its own not unsignificant cost)
- link: [Rich Hickey](https://twitter.com/richhickey)'s talk [Simple Made Easy](https://www.infoq.com/presentations/Simple-Made-Easy)


### 15:00 in Wotton 1 - [Tom Oram](https://twitter.com/tomphp) - TDD Design Patterns
- [wiki from the session](https://github.com/lscc/socrates-uk/wiki/TDD-Cheating-Followup---TDD-Design-Levels)
- identify patterns in tests which indicate a production code problem
- [Tom](https://twitter.com/tomphp)'s [slides](https://www.slideshare.net/TomOram/tdd-design-patterns-socrates-uk-2019) show how adding a conditional to the production side might multiply the number of test cases that we need to write
- [JB Rainsberger](https://twitter.com/jbrains)'s talk: [Some Underrated Elements of Success for the Modern Programmer](https://www.youtube.com/watch?v=mbcV_Qdb7Ts)
  - 3 stages of TDD: mistakes (test-first development), design (test-driven development), patterns (problems in tests translate to problems in code)
- [Michael Feathers](https://twitter.com/mfeathers)'s talk: [The Deep Synergy Between Testability and Good Design](https://www.youtube.com/watch?v=4cVZvoFGJTU)


### 16:00 in Wotton 2 - [Maaret Pyhäjärvi](https://twitter.com/maaretp) & [Sharath Byregowda](https://twitter.com/sharathb) - Mob testing rock-paper-scissors
- [Sharath](https://twitter.com/sharathb) had implemented rock-paper-scissors in 4 different ways, with computer using different strategy in each way
- our goal was to form a team of testing mob who is trying to figure out what the 4 types of logic are
- we had one person on the keyboard (driver) who had to wait for instructions from 1 decision maker (navigator). Navigator would take their decision given the discussion of the whole team.
- we rotated every 3 minutes
- [Maaret](https://twitter.com/maaretp) explained the 3 levels of navigation:
  - intent (please choose a gesture),
  - location (please choose a rock)
  - details (please hit enter, then type rock, then confirm with enter)
- ideally the navigator should start with intent and only move up the level of details if required (for example focusing too much on IntelliJ shortcuts is too detailed; better start by letting the driver figure out how to do the task themselves)

<div style="text-align: center">
  <a href="/pic/2019-socratesuk/testing-mob.jpg" target="_blank">
    <img style="width: 80%; height: 80%; margin: 1em" src="/pic/2019-socratesuk/testing-mob.jpg"/>
  </a>
</div>


### Evening
- [Oliver](https://twitter.com/ollispieps) explained how he's recently been working in 2 minutes increments (commit or revert after 2 minutes) in order to have very fast feedback loops
- he has been using [Arlo Belshee's commit notation](https://github.com/RefactoringCombos/ArlosCommitNotation) which shows a level of risk associated with each commit
- [Oliver](https://twitter.com/ollispieps) recommended looking into [Wardley maps](https://medium.com/wardleymaps) as an effective communication tool
- an example of an application of [Wardley Maps](https://medium.com/wardleymaps) is this talk: [Why the fuss about Serverless](https://www.youtube.com/watch?v=b7Nc_FJiosk)
- we played [Werewolf](https://en.wikipedia.org/wiki/Mafia_(party_game\)) till late night


More links
-------------------------------------------------
- [wiki for all the sessions](https://github.com/lscc/socrates-uk/wiki/2019-Sessions)
- [photos by Esko Luontola](https://www.dropbox.com/sh/lyuxdvasb2xpw8p/AAAatEt8MigElskEuxH83C-sa?dl=0)


Summary
-------------------------------------------------
- one of my favourite moments at the conference was when I was at the [Retrospective on writing a book](https://github.com/lscc/socrates-uk/wiki/Retrospective-on-Writing-a-Book) session and [@sleepyfox](https://twitter.com/sleepyfox) walked into the room looking for another session [Help Me Get Over Corporate Bullshit](https://github.com/lscc/socrates-uk/wiki/Help-Me-Get-Over-Corporate-Bullshit) and asked us "Is this bullshit?" only to hear "Oh, that's next door" :)
- thanks to all the organisers, facilitators and participants - hope to see you soon again :)
