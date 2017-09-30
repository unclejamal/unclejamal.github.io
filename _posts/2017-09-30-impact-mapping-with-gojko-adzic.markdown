---
layout: post
title: Impact Mapping Workshop with Gojko Adzic
---

On 27 September 2017 I participated at the full-day [Impact Mapping workshop](https://skillsmatter.com/courses/560-gojko-adzic-impact-mapping-workshop) which took place at [Skills Matter](https://skillsmatter.com) in London. This post is a summary of how I experienced it.


Format
-----------------
- from 9:00 till 17:00,
- 1 coffee break in the morning, 1 lunch break, 2 coffee breaks in the afternoon,
- 3 groups of around 5 people each,
- most of the day working iteratively on the group exercise and getting Gojko's feedback after each iteration,
- fast-paced but not sense of rushing (iterations were short but enough to open us for the following explanations from Gojko).


Introduction 9:00-9:30
-----------------
- what is Impact Mapping?
- *Task for participants* - write on post-its what you want to learn today. Post-its were put on the wall and were answered one by one in the late afternoon until people were happy with the answer


Group exercise - Create Plan
-----------------
Problem: the existing legacy application is an information gateway for music-related events. It serves Music Fans (mostly young people getting updates about their favourite bands or events) and Event Organisers (newsletters, lists of atendees, analytics).


The legacy application uses email as a delivery channel which presents us with the following challenges:

- Gmail filters out emails into their Promotions tab,
- fans like to get updates from social media pages rather than from emails,
- people use smartphones => small screens
- cloud makes scaling more advances technologies cheaper and easier


Imagine you're in charge of a full rewrite project. You've got a big budget and people. You're expected to restore confidence we can deliver something. Create a plan of work for the next 5 iterations.


Our answers:

- generally a bunch of features which we felt would be nice (no metrics to back them up, no overarching theme)


Idea: when working on brain-storming-like, creative, innovative tasks - split people into groups and they will create similar but different ideas:


Group exercise - Sell Your Plan To All Groups
-----------------
Compare plans for the 3 groups:

- some groups argued that their plan is best because it does cloud computing. Some other groups argued their plan is best because it avoids it for now,
- some groups argued that their plan is best because they tackle high-risk first. Some other groups argued tackling low-risk first was preferable,
- some groups argued that their plan is best because it involves all stakeholders. Some other groups prefered to limit it to 1 stakeholder only.


Generally, when comparing things, it's easy to interpret them in a way that justifies our (biased) position.


Story from Gojko:

- there was an airline that claimed that they made huge profit by removing a row of seats from their planes. After all, it speeded up booking process, it slightly raised a price per seat, it reduced the overall luggage weight so fuel costs could be lower, etc.
- around the same time another airline claimed that they made huge profit by adding a row of seats in their planes. After all, they could sell more tickets, cost of flight per passenger was lower, etc...
- conclusion: anything can be used to justified our position
- conclusion: it's hard to argue about such ideas upfront


Group exercise - What To Measure?
-----------------
So how do we know our work plan is going to improve things?


Gojko referenced Ron's work:

- comparing goals from Powerpoint presentations (new markets, large scale, and other big words...) to actual project outcomes
- around 1/3 of projects did improve metrics for the Powerpoint goals
- another 1/3 didn't change the promised metrics at all or changed them neglibibly
- last 1/3 actually damaged the metrics


Task for participants:

- Investors are happy to pay for all 3 groups to do their initial 5 iterations and then choose the best candidate
- how do we decide who's best? (what metrics?)


Our answers:

- no of organisers,
- no of events,
- conversion rate (from event notification till ticket purchase),
- existing Music Fans retention,
- existing Event Organisers retention,
- number of followers on our Facebook fan page
- revenue growth


Comment from Gojko:

- participants had different understanding of the word retention (does it apply to new or existing Fans? are we measuring the total number of Fans or the number of Fans who left? etc...)
- participants had different understanding of how to measure these things (is growth measured in GBP or in percentage, for what time frame, is it fair to measure revenue if big festival dates are outside of our control?)


Gojko quoting somebody:

- "most businesses measure things that are easy to measure rather than the valuable ones"
- User Story points (or Burndown points) are a proxy metric for actual value (it's easy to measure it but it represents time/effort spent rather than a value increment)


So which metrics do we want to focus on now (in our current stage):
j
- some metrics are outside of our scope (like number of tickets sold which depends highly on big festival dates)
- some metrics cannot be compared across our 3 Prove of Concept solutions (number of followers on Facebook doesn't make sense for solutions which skip social media for now)
- short-term metrics are different from long-term metrics (time factor)


Most of software projects suffer from the Underpants Gnomes syndrome (from South Park):

- there's plenty of features to work on and then they some how make our business happy (create profit)
- source: https://en.wikipedia.org/wiki/Gnomes_(South_Park)

![Underpants Gnomes syndrome](https://upload.wikimedia.org/wikipedia/en/d/dd/Gnomes_plan.png "Underpants Gnomes syndrome")


Reference to a document: [Why FBI can't build a case management system?](https://www.computer.org/csdl/mags/co/2012/06/mco2012060073-abs.html) by Jerome Israel

- FBI tried doing it in an iterative way,
- they were measuring User Story points (which actually measures effort/time),
- they were redefining business goals for "each" iteration simply to justify what they worked on last,


Reference to a book:

- pick one metric that matters (for the time period in question),
- (or at most a few).


From the book [Lean Analytics](http://leananalyticsbook.com) - good metrics change depending which stage a project is in:

- Empathy -> Stickiness -> Virality -> Revenue -> Scale
- empathy - first make users like your application,
- stickiness - then make them stay using it longer,
- virality (growth) - reduce cost of aquisition of new users,
- revenue,
- scale - cost of operation


Hence, using this model we can see:

- what not to do: e.g. investing lots of money into virality-promoting-marketing which gives us lots of newcomer users but they never come back
- that when improving, say revenue, we might be potentially loosing a bit of virality but not too much (the model creates a framework for a discussion)
- any product is likely to be in one of those stages, and looking at the metrics for the wrong stage might be misleading (wasting effort)
- it's possible that a product falls down to a lower stage (e.g. our Email application from the Group exercise was at Scale but now fell to, say, Stickiness, i.e. we're losing people quickly)


When deciding what to work on next possible categories are:

- Must/Should/Could - Gojko's prefers other categories,
- [Chris Matts](https://twitter.com/PapaChrisMatts)'s: now vs not now (or more politically correct rephrased: yes vs yes but later)


Don't prioritise features (it's hard/impossible to do well). Prioritise business goals:

- as a side effect it also limits the scope drastically)


Question from a participant:

- what if management in my project only wants to talk about "revenue"?
- that's fine if the project is in the "revenue" stage - but what metrics do we use to measure it?
- but if we're in an earlier stage, we likely are wasting our efforts trying to maximise the revenue


Anthony wrote a book [What customers want?](https://www.amazon.co.uk/What-Customers-Want-Outcome-Driven-Breakthrough/dp/0071408673) about his lesson that costed him $1.7bln:

- ! the most important takeaway from the workshop,
- it is the answer to the Underpants Gnomes syndrome,
- 1/3 to 1/2 of all ideas what to build are "wrong" - how to detect them early, ideally instead of wasting a lot of effort?
- plan in terms of *behaviour changes*,
- *behaviour changes* are observable/measurable in short term,
- a User Story format can be used for that: As a Music Fan, In order to find out about interesting events in my location _faster_, I want an sms notification,
- adverb 'faster' implies a *behaviour change* - other examples: slower, more frequent, cheaper, easier (with shorter journey),
- focusing on *behaviour change* allows us to compare different solutions more easily - the question is how do they improve the metrics for the *behaviour changes* and goals,
- *behaviour changes* are *Impacts*
- *behaviour changes* also allow to slice User Stories per Actors, for example release this feature for heavy metal fans only or for Norway only) and observe the Impact there first,


A hierarchical model:

- Goal => *behaviour changes* => epics => user stories => specifications
- Goal is achieved by 1+ *behaviour changes*, which are caused by delivering epics, which constist of user stories, which are defined by specifications



Group exercise - Define Behaviour Changes
-----------------
Examples from the participants (some crossed out by Gojko to indicate: not helpful in solving the problems from Exercise Description):

- Music Fans will buy tickets more frequently,
- ~~Music Fans will buy tickets faster (shorter user journey)~~,
- Music Fans will share the events more often in social media,
- Music Fans will start consuming event information on the move (on smarthphones),
- Music Fans will start attending events they didn't search for,
- Event Organisers will start posting events on the move,
- ~~Event Organisers will post more detailed info about events~~,
- ~~Music Fans will switch from email to social media~~,
- ~~Event Organisers will reply faster to potential problems~~,
- ~~Event Organisers will send more targetted offers~~,
- Music Fans will click more links / more often / sooner,
- ~~Music Fans will attend events more frequently~~.


Question from the participants: Isn't it hard to measure some metrics in software systems?

Answer: If you design systems with metrics in mind, it becomes easier to measure them (just like with testability in Test-Driven Development)


New Goal Statement: let's assume that our business decided the most important thing for now is to "protect the existing revenue" (other possible goals being, e.g. "moving to the new business model"). Then the 2 behaviour changes we chose to focus on were:

- Music Fans will click more links / more often / sooner,
- Music Fans will start consuming event information on the move (on smarthphones).


Group exercise - Redo "Create Plan" Exercise
-----------------
Having the new goal and the 2 behaviour changes in mind, we changed our plan:

- add social channels,
- optimise templates for emails,
- SMS notifications (on the move)

If the 2 first features get Music Fans to change their behaviour in acceptable way (e.g., 20% or more clicks), we can stop development there and move on to the next behaviour change supporting our Goal.

The Deliverables (User Stories) from our plan can be further split, e.g. by Actors - just deliver SMS notifications to people in London (it simplifies the feature to be just 1 SMS gateway and 1 language only). Location can be chosen for many reasons:

- lowest risk,
- changes most needed,
- simplicity, etc.


Impact Maps
-----------------
Quote: Magic happens in the Impacts

- some companies dropped Actors to emphasise Impacts
- Gojko likes Actors for slicing Deliverables down and prioritisation ("which roup should we address first?")


2 ways to create Impact Maps:

- take existing backlog and reverse engineer it (possibly a common place to start it in most of companies)
- start from Goals (probably cleaner but in practice happens less often)


Common mistakes with Impact Maps:

- Actors overly generic - e.g. "User". Better be specific, e.g. "people in Norway" (different Impacts),
- hard to identify behaviour changes (Impacts),
- sequences - "yes, we can make it cheaper, faster, bigger but what first?".


Group exercise - Decide Goals, Actors, Impacts, Deliverables
-----------------
Assume "more clicks" behaviour change is achieved. Now we want to do more (cut-outs pieces should be assembled into an Impact Map)


Questions:

- what is a Goal?
- what is an Impact?


Answers: : [Impact Mapping cheatsheat](https://github.com/impactmapping/open-impact-mapping-workshop/blob/master/educational-workshops/concerts-online/handouts/cheatsheet.doc) explaining Goals, Actors, Impacts and Deliverables


Goal:

- organisation gets something out of it
- not an impact on someone's behaviour
- doesn't imply a solution


Impact:

- start/stop doing something
- do something differently (faster/easier/cheaper/etc.)
- not Deliverables (not software ideas or implied solutions)


Order of Goals:

- "you can get everything at the end but what's the very next thing?"
- you can't compare Goals - it's not about what's most important - it's about the sequence


Perspectives:

- User's
- Customer's
- Organiser's


Example of Perspectives - Google Homepage:

- Users want to find relevant information,
- Customers pay for the ads so their goal is to distract people and send them somewhere else,
- Organiser - find a balance between the goals of Users and Customers


"Music Fans will unsubscribe less frequently" is a behaviour change that's always wanted. The question is "does it support our primary Goal"?


To test Impact Maps a question can be asked:

- e.g. "what happens if we get no new subscribers but we manage to reduce unsubscriptions?"



Group exercise - Create Impact Map For a Goal
-----------------
Pick goal "Reduce reliance on a single channel (5-10% messages not email, click rates ok") and create an Impact Map for it.


Actors:

- existing subscribers
- travellers


Impacts:

- start getting updates via alternative channels
- discover events easier


Deliverables:

- WhatsApp gateway integration,
- WhatsApp subscribe web page,
- "Switch from e-mail to WhatsApp" link on unsubscribe pages,
- SMS subscribe web pages,
- "Get SMS updates" link in newsletter,
- SMS gateway integration,
- Event update calendar feeds,
- Send short message about event changes,
- "What's on tognith" web site,
- "Insider alert" calendar feeds for popular travel destinations.


We can compare Deliverables only if:

- we know Impacts, Actors, Goals


We can deliver some Deliverables only for a subset of users:

- apparently Australians compare a lot about Facebook - that's because it new features are delivered first in there to see if they're successful before reaching bigger markets like US
- [online experiments at Microsoft](http://exp-platform.com/experiments-at-microsoft)

Craig Larman defines 2 kinds of User Stories:

- earning story,
- learning story - example: building a social network for only 10k people to see how often they play games (10k size is small and thus simplifies the technical implementation)


3 dimensions to fail:

- time - the longer the time horizon, the harder to make assumptions (Google Plus integration was a must-have idea some years ago),
- human - a trading system had to be rewritten to scale better; once completed it was shown to a CEO which was offended that his old platform was rewritten and cancelled the project,
- local - Facebook Messenger is used in US but not in China; Android vs iPhone vs Desktop.


According to Tim Harford's book [Adapt](https://www.amazon.co.uk) successful plans consist of 3 ingredients called the [Palchinsky Principles](https://en.wikipedia.org/wiki/Peter_Palchinsky):

- variation - options, new ideas,
- survivability - experiments should be safe (rather than sticking all time/money/effort into 1 basket),
- selection - use feedback (if enough impact is made in 1 area, move on to the next thing)


Question from the participants: "What if my senior tells me I absolutely have to do US1, US2, ..., US20 and leaves no room for changes"

Answer: respond "yes, but in what order?" Once engaged in discussion they will notice that perhaps not all the User Stories were needed (or that more was needed to make an impact)


2 sides of Impact Mapping:

- play politics at the higher level - to decide the Goals,
- reporting tool - progress on Impacts and Goals


Question: I'm working on a rewrite project...

Answer: Pretend that I can give you the rewritten application right now. If that happens, whose behaviour will be easier to change?

- e.g. it will become easier to integrate with systems of our clients,
- e.g. operations team cost will be lower


Alternative:

- pick 1 US with low risk and measure the ration for our work vs their work,
- initially it will be 100% us - 0% them,
- later hopefully 10% us - 90% them,
- perhaps in the end the big rewrite won't be needed (it wasn't in Gojko's case).


Cost of delay:

- for Deliverables is almost impossible to calculate,
- for Goals/Impacts is easy.


Measurements and Milestones:

- scale - what will you measure (e.g. user retention),
- meter - mechanics of how to measure it (e.g. attendees with more than 1 event per month),
- benchmark - current state (e.g. 120) (if no data available, maybe the market has the data; or create a learning story for a subset of users to get a benchmark),
- target - desired state (e.g. 200 by March),
- constraint - failure level (e.g. below 80 is unnacceptable)  (this one can be used to open a discussion more easily)


Group exercise - Reverse Engineer Underpants Gnomes Situation
-----------------
How to demonstrate that a chosen Goal is wrong and misleading?


Let's assume a Goal was picked:

- "send more emails"


And Deliverables were asked for:

- 0 Topic Subscriptions
- 1. Sending Screen - 1A Tag by topic, 1B Tag by location, 1C Filter emails by tag
- 2. Subscription screen - 2A Subscribe to topic


To prove the Goal is nonsense:

- reverse engineer the Impacts created by the Deliverables,
- create metrics for Impacts (metrics are something tangible and concrete so it will be easier to spot the nonsense),
- notice that the Impacts and metrics don't support the Goal
- question: so what is our actual Goal? (it should be as concrete as possible)
- question: look for better options for Impacts and Deliverables with respect the new Goal


In our case the Impacts of the Deliverables will be, e.g.:

- Music Fans will find the content faster,
- Music Fans will unsubscribe less.


In our case the metrics to identify failure points:

- e-mail to unsubscription ratio,
- no of subscribers per tag (high number could cause technical failure),
- no of tags per location


Thus:

- nobody is talking about e-mails we're sending because it's a nonsense goal
- the impacts would possibly result in sending more e-mails, but the easiest way to achieve that "Goal" is to just spam the users
- so what is the actual Goal? (perhaps Customer Retention or Grow Revenue, with Impacts such as "Find the content faster" or "Unsubscribe less")
- but if thath's the Goal, what other options do we have to satisfy it - except of the proposed Deliverables? (perhaps an Android app will bring much more revenue)

More details on Goal refinement: [here](https://github.com/impactmapping/open-impact-mapping-workshop/blob/master/educational-workshops/concerts-online/facilitation-guide.md#exercise-5-propose-new-delivery-plans)



4 ways to use Impact Maps
-----------------
Gojko met up with Ingrid Domingues and Johan Berndtsson [link1](https://gojko.net/2014/11/17/how-to-get-the-most-out-of-impact-mapping) [link2](https://www.infoq.com/articles/most-impact-mapping) to compare how people use Impact Mapping:


Depends on 2 factors:

- ability to make investments (ATMI),
- consequences of being wrong (COBW).


Good ATMI, small COBW (Iterate)

  - small Impact Maps (commonly less than 7 Impacts, less than 10 Deliverables),
  - direct and immediate feedback from frequent deployments to production,
  - customer research can be done on a subset of users,
  - start with a rough map and evolve it over time,
  - can be drawn on whiteboards.

Poor ATMI, small COBW (Align)

  - multiple decision makers competing for the same resources/budget,
  - challenge: selecting among many different initiatives within the company,
  - common in large finances,
  - Impact Maps help align all stakeholders for larger milestones,
  - commonly several maps, rather than just one,
  - often digitilised,
  - bigger maps,
  - progress checks: "have we delivered it already?",
  - usually only parts of maps end up getting delivered,
  - Impact Maps go to levels of Impacts,
  - story maps.

Good ATMI, serious COBW (Experiment)

  - serious COBW - perhaps high product risk,
  - organisations can explore different product options,
  - we need more certainty,
  - trying out options in research needed to actually deliver,
  - story maps.

Poor ATMI, serious COBW (Discover)

  - innovative physical products, medical devices, huge financial risks,
  - we need more certainty,
  - research needed to created a product backlog.



Story Mapping ties back to Impact Mapping:

- story maps are behaviours
- Impact Maps are changes in behaviour


Behaviour changes allow to:

- prioritise,
- do research on something,
- clarify how to do things.


How Google changed colour of links on their Homepage:

- [The Guardian article](https://www.theguardian.com/technology/2014/feb/05/why-google-engineers-designers),
- [CNET article](https://www.cnet.com/news/google-designer-leaves-blaming-data-centrism),
- humans are unpredictable



Introducing Impact Mapping at work
-----------------
Question: how to deal with people who "don't want to play post-its?"

Answer:

- you don't have to play post-its. Just ask questions about behaviour changes,
- measure things in production to prove/disprove ideas (like Google staff did with the colour of links),
- don't sell "solutions" - sell "problems" and let the solutions emerge (e.g. "it will take forever...")
- book [Switch: How to change things when change is hard](https://www.amazon.co.uk/dp/B005TKD512) by C. & D. Heath



Wrap up 16:00-17:00
-----------------
- answering each question from the Introduction
- offering "lifetime technical support" - in case of questions, use Impact Mapping mailgroup and Gojko will try to respond within 2 business days (wow!)


Handouts
-----------------
- a copy of the [Impact Mapping book](https://www.impactmapping.org/book.html)
- a copy of the [Fifty Quick Ideas To Improve Your User Stories book](https://fiftyquickideas.com/fifty-quick-ideas-to-improve-your-user-stories)
- printouts of the group exercise instructions
- printouts of the [Impact Mapping cheatsheat](https://github.com/impactmapping/open-impact-mapping-workshop/blob/master/educational-workshops/concerts-online/handouts/cheatsheet.doc) explaining Goals, Actors, Impacts and Deliverables


Links
----------
- [Impact Mapping website](https://www.impactmapping.org)
- [workshop materials and facilitation guide](https://github.com/impactmapping/open-impact-mapping-workshop)
- [Related resources online](https://www.impactmapping.org/related.html)
- [Impact Mapping group](https://groups.google.com/forum/#!forum/impact-mapping)
- [Impact Mapping book](https://www.impactmapping.org/book.html)
- [Fifty Quick Ideas To Improve Your User Stories book](https://fiftyquickideas.com/fifty-quick-ideas-to-improve-your-user-stories)


Thanks to
----------
- [Gojko Adzic](https://twitter.com/gojkoadzic) for the fantastic workshop
