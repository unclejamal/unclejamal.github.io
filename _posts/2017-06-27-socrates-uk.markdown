---
layout: post
title: SoCraTes UK 2017
---

During 15-18 June I participated at the [SoCraTes UK 2017](http://socratesuk.org) (Software Craftsmanship and Testing) unconference which took place at Wotton House [Wotton House](https://www.phcompany.com/de-vere/wotton-house/) in Dorking. This post is a summary of how I experienced it.


Thursday, 15th June
-------------------
The evening was spent pairing with [Iulian Ghionoiu](https://twitter.com/julianghionoiu) on the Roman Numerals kata with 2 twists: we wanted to use property-based testing (we tried Kotlintest for Kotlin) and to evolve the requirements for the conversion (as though the final version of the Roman/Arabic numbers hasn't been discovered yet). The evolution meant starting with only I's (scratching a piece of wood or carving a line in the stone?). Then, we tried to imagine what problems that representation presented before coming up with solutions. The problems were:

- countability (ten I's carved next to each other blur into each other when trying to count them) -> solution: introduce new symbols that look different like V (note that V here stands for one and can be placed at any position)
- additivity (even though we have a visually different character, we still have to spend time counting each single one) -> solution: make some symbols stand for more than 1. At that point V could become to mean 2, 3, 5 etc. Generally the more people had to count, the more symbols they need
- comparability (even though we have relatively short 'roman' numbers due to characters representing different values, we still can't compare them easily) -> solution: introduce order of symbols so that it's obvious at one glance two representations are the same (like. IIXIX == XIIIX, so let's write them as XXIII or IIIXX)

We were pleased to find out that [one of the hypotheses behind the origin of roman numerals](https://en.wikipedia.org/wiki/Roman_numerals#Tally_marks) was similar to our reasoning and states that *the system was neither additive nor subtractive in its conception, but ordinal*.

One other fun twist was that we were test-driving 2 functions simultaneously (convertRomanToArabic() and convertArabicToRoman()) by starting with the property-based test, which locked them to have to change at the same time:

{% highlight java %}
convertRomanToArabic(convertArabicToRoman(x) == x
{% endhighlight %}


Friday, 16th June
-----------------
### 10:00 in Azalea - [Alistair Smith](https://twitter.com/alastairs) - Help me model my domain (DDD)
- core domain, support domain, generic domain - focus on core
- ubiquitous language is shared with all parties. But there will be internal things that you have to name that your users/business won't get to see


### 11:00 in Azalea - [Oliver Nautsch](https://twitter.com/ollispieps) - Consumer Driven Contracts (CDC)
- [instructions and code](https://github.com/ollin/cdc-workshop)
- ask your clients what they need (some people don't like it)
- format: code first + then discussion (was effective in Oliver's experience)
- that project used CDC because they were splitting a monolith
- they also used some integrated testing after running CDC but not too much (testing pyramid)
- their integrated tests were quick (things were orchestrated with Kubernates)
- 3 ideas how to share CDC in an organisation:
1) Check in directly into Provider's repository
2) Have Provider download the latest zip of your pacts from artifactory
3) Have Consumer build automatically commit in the Provder's repository


### 12:00 in the garden - [Aki Salmi](https://twitter.com/rinkkasatiainen) - Opinions about opinions (being opinionated)
- it's not emotions to suppress, it's attachment to opinions
- listen to body language to see when emotions arise (at which point I stop listening)
- try to make it win-win (rather than compromise, or pushing your own opinions)
- try thinking in terms of pros and cons (and trade-offs) rather than right or wrong
- even if you have heard arguments of the other camp (e.g. outside-in testing vs bottom-up), still listen to your vis-a-vis to understand to understand why their opinion is particularly important for them in this very context
- listen to their opinion first, rephrase their opinion with your own words
- things just are (they're neither right nor wrong)
- [Aki](https://twitter.com/rinkkasatiainen) runs training in organisations on "how to listen to others"
- opinions are a quest to understand the other person (so that they get the experience of being truly understood)
- what if my opinions don't matter to anybody... except of me?


### 14:00-16:00 in Wotton 2 - [Johan Martinsson](https://twitter.com/johan_alps) - Bugzero (hands-on)
- refactoring sources of potential bugs away (not actually bugs - yet)
- instructions under: [https://github.com/martinsson/BugsZero-Kata](https://github.com/martinsson/BugsZero-Kata)
- blog post: [5 steps to Mistake Proof Software Design](http://mozaicworks.com/blog/5-steps-to-mistake-proof-software-design)
- blog post: [It's not a configuration issue. It’s a design issue](http://martinsson-johan.blogspot.co.uk/2016/06/its-not-configuration-issue-its-design.html)
- book: [Usable Software Design](https://leanpub.com/usablesoftwaredesign) by [Alexandru Bolboaca](https://twitter.com/alexboly)
- talk recording: [#BugsZero - Agile Singapore Conference 2016](https://www.youtube.com/watch?v=gQR1NlkgLZU) by [Arlo Belshee](https://twitter.com/arlobelshee)
- I was pairing with [Ivan](https://twitter.com/ivanrmoore) and [Rainer](https://twitter.com/matschmann)
- Three steps works: 1) Identify weakness of design. 2) State what the potential bug is. 3) Refactor the code to prevent it.
- what techniques are available to make things more DEV-UX-friendly?
- [Ivan](https://twitter.com/ivanrmoore)'s automated IDE refactoring


{% highlight java %}
public void printStuff(int place) {
  System.out.println( "I was at " + place );
}
{% endhighlight %}

We wanted to push System.out.println up the call stack (that is make the printStuff return the String)

{% highlight java %}
public void printStuff(int place) {
  System.out.println( textValue(place) );
}

private String textValue(int place) {
  return "I was at " + place;
{% endhighlight %}

Now printStuff can be inlined which will push System.out.println to the caller and leave textValue in the class.


### 16:00 in Azalea - [Julian Harty](https://twitter.com/julianharty) - TDD with content
- how to test systems which correctness depends on the data, given production data is sensitive and cannot be used by the development team
- e.g. do long names from the database render gracefully in the GUI
- e.g. handling Cyrillic, Arabic, Chinese etc. characters
- e.g. performance of queries might depend on the data shape
- a solution might be "Clean Door + Dirty Door" (IBM Bios table of interrupts), where the Clean Door team (having access to production data) can run algorithms prepared by the Dirty Door team (development team) which will characterise the production data, e.g. longest name, what encodings are used, distribution of first names (apparently one third of European first names start with "j"), etc. Then the Dirty Door team will implement a data generator which matches the production characteristics.


### 17:00 in Wotton - Retrospective
- useful when learning a programming language -> [Exercism](http://exercism.io) (should teach idiomatic solutions)


### 18:00 in Wotton - [Esko Luontola](https://twitter.com/orfjackal) - Lightning talks
- [auth0](https://auth0.com) - few lines of code to get sign ins for free

### 18:00 in Wotton - Lightning talks
- asking important question on HipChat and getting no answer? Why? Because I didn't explain why it's important. 
- why am I asking the question? What the cost of them not answering the question is? What could I do if I don't get an answer?
- e.g. "I need to make decision by Friday for the meeting. But if you don't give me the answer till then, here's what I'm going to do"
- provide context for people + respect their time + provide TL;DR (expand gradually)


### 21:00 in 1877 (posh) - Werewolf


Saturday, 17th June
-----------
### 10:00 in Aster - [David Green](https://twitter.com/activelylazy) - Titanic Death (predictions with machine learning)
- online course (12 weeks) is available at [coursera](https://www.coursera.org/learn/machine-learning)
- machine learning - simple maths that predicts the curve and calculates the cost function (how far is the guess curve from the reality) and then does the "gradient descent" to minimise the cost function
- data for Titanic passengers: [https://www.kaggle.com/c/titanic/prospector#877](https://www.coursera.org/learn/machine-learning)


### 11:00-13:00 in Wotton 2 - [Sandro Mancuso](https://twitter.com/sandromancuso) & [Pedro Santos](https://twitter.com/pedromsantos) - Designing Microservices
- identifying microservices from business rules
- applications were derived from user journey
- tool for sequence diagrams: [https://www.websequencediagrams.com](https://www.websequencediagrams.com)
- workshop started by group drawing sequence diagrams at the service level (start with the browser)

{% highlight java %}
title List of product Flow [QUERY]

Browser->+Content: getPage()
Content-->-Browser: SPA

Browser->+GetProductList: get(country, numOfProductsToRetrieve)

GetProductList->+ProductCatalogue: get(country, numOfProductsToRetrieve)
ProductCatalogue->-GetProductList: [ ProductInfo{PID, basePrice, ExtraInfo} ]

GetProductList->+Availability: get([PID])
Availability->-GetProductList: [ {PID, quantityAvailable} ]

GetProductList->GetProductList: Satisfy numOfProductsToRetrieve

GetProductList->+Pricing: get([PID, productType, availablity])
Pricing->-GetProductList: [ {PID, price} ]


GetProductList-->-Browser: numOfProducts * {productInfo, price, quantitytAvailable}

Browser->+Content: getProductContent()
Content-->-Browser: Images, Videos
{% endhighlight %}

Microservices have a huge cost (you can't even experiment with it like with a single codebase) so let's stress test our design:

- what would happen if Price Service goes down?
- how many HTTP calls do we have to make per single user request?
- when I'm in Spain but want to deliver to London, how does that impact things I'm adding to basket?
- can I deal with multiple delivery companies?
- ... if these things cause ripple effect across multiple applications and it's EXTREMELY hard to change these things with microservices
- ... if a microservices in the sequence diagram does only 1 thing, is its existence justified
- ... perhaps I could merge microservices based on the availability (they both have to be up together in order for the whole webapp to be usable)
- ... if Sales and Promotions are done by different people, putting them in one microservice might mean that the team in charge won't have easy access to one of the groups (Conway's Law)

[Sandro Mancuso](https://twitter.com/sandromancuso) & [Pedro Santos](https://twitter.com/pedromsantos) did this in the past in a real project:

- first discuss with business people and different teams, what are the main features (it might take 3 hours to come up with 12 bullet points)
- draw sequence diagrams for these features ,with vertical blocks being just concepts (rather than applications) -> just to get understanding how it works
- extract bounded contexts and then group them by first- and second-level (ex. below)


{% highlight java %}
First-level (public) bounded contexts -> Second-level bounded contexts
-----------------------------------------------------------------------
Catalog -> Media, Product, Tax, Pricing, Availability
Delivery -> Availability, Distribution
Order -> Mailer
Cart -> Promotions
Payments
Customer
{% endhighlight %}

- should Tax bounded context  be a microservices, or just a component within Pricing Service?
- if in doubt, keep them together (perhaps later extract when they grow)
- different "channels" (web, mobile, etc) you might be getting different first-level bounded contexts
- if company has already microservices (and they're struggling with them), just do this exercice as though you were starting from scratch (perfect scenario) and then compare current design with the perfect and see how you can evolve there


### 14:00 in Azalea - [Ian Russell](https://twitter.com/ijrussell) -  Strategic Domain Driven Design
- [https://github.com/lscc/socrates-uk/wiki/Strategic-Domain-Driven-Design](https://github.com/lscc/socrates-uk/wiki/Strategic-Domain-Driven-Design)
- domain -> subdomains (core, supporting, generic)
- bounded context
- ubiquitous language
- context map -> shared kernel, anti-corruption layer, customer-supplier


### 15:00 in the garden - [Aki Salmi](https://twitter.com/rinkkasatiainen) - How to make a safe space
- Finnish hiking society mentions 4 types of safety: physical, spiritual, social, psychological


### 16:00 in 1877 (posh) - XP Cards [Dionatan Moura](https://twitter.com/dionatanmoura) - Extreme Programming Playing Cards
- made by Industrial Logic - [link](https://www.industriallogic.com/blog/xp-playing-cards)
- game master plays a Problem Card on the table
- players try to act by presenting a Solution Card or a Value Card
- discussion follows what's the best response to the Problem


### 17:00 in Wotton 1 - [David Heath](https://twitter.com/dgheath21) - Liberating structures
- [website](http://www.liberatingstructures.com) and [book](https://www.goodreads.com/book/show/21481308-the-surprising-power-of-liberating-structures)
- how to facilitate meetings so that everybody gets a voice
- we tried: [1-2-4-all](http://www.liberatingstructures.com/1-1-2-4-all) and [impromptu networking](http://www.liberatingstructures.com/2-impromptu-networking)
- [David Heath](https://twitter.com/dgheath21) mentioned other techniques: [15% solutions](http://www.liberatingstructures.com/7-15-solutions) (small contributions add up if done by many), [TRIZ](http://www.liberatingstructures.com/6-making-space-with-triz) (fixing bad things), [troika consulting](http://www.liberatingstructures.com/8-troika-consulting)


### 23:00 in Bay - [Sandro Mancuso](https://twitter.com/sandromancuso) - Mob Programming
- kata: KatacombsOfDoom - [github](https://github.com/sandromancuso/KatacombsOfDoom)


Sunday, 18th June
-----------------
- hiking to Leith Hill
- [Riccardo Novaglia](https://twitter.com/RNovaglia) pointed out there's a game similar to Werewolf and it's called [The Resistance](https://en.wikipedia.org/wiki/The_Resistance_%28game%29)


Some Interesting Sessions I didn't participate in
-------------------------------------------------
### [Johan Martinsson](https://twitter.com/johan_alps) - Accelerated Learning
- [decks](http://llewellynfalco.blogspot.co.uk/p/sparrow-decks.html)
- learning to differentiate concepts by a machine-learning-like technique
- e.g. how to differentiate between two kinds of sparrows that we don't know anything about. Instead of conscious learning, we're presenting our brain with a big sample of images of each kind and the right answers. At some point the brain will figure out what the difference is (sometimes even without being conciously aware of it)


### [Matthew Butt](https://twitter.com/bnathyuw) - Church Bells
- apparently the sounds produced by church bells in England are algorithmic. The sequence of notes is constantly changed by swapping the position of each two adjacent bells (or otherwise) so that each iteration results in a new sequence. The trick is to come back to the original sequence with each iteration being unique.


Next year
----------
- take a rucksack to carry around a laptop and a charger


Thanks to
----------
- [Matthew Butt](https://twitter.com/bnathyuw) for his fantastic facilitation of the event
- [Johan Martinsson](https://twitter.com/johan_alps) for explaining his Accelerated Learning session at the dinner
- [Riccardo Novaglia](https://twitter.com/RNovaglia) for being superkind and offering me a lift to London
- all the participants for the sessions, conversations and lots of fun
