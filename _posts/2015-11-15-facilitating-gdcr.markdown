---
layout: post
title: Facilitating a Global Day of Code Retreat
---


On 14/11/2015 I had an honour to co-facilitate, together with [@keyvanakbary](http://twitter.com/keyvanakbary), a [Global Day of Code Retreat at TransferWise](http://www.meetup.com/london-software-craftsmanship/events/226148869). This blog post is my retrospective on what we did and how we could improve it for the next year.

<div style="text-align: center">
  <a href="/pic/gdcr2015/gdcr.jpg">
    <img src="/pic/gdcr2015/gdcr-mini.jpg"/>
  </a>
</div>



Before the day
--------------------------
I met [@keyvanakbary](http://twitter.com/keyvanakbary) a few days before and we discussed organisational matters as well as the ideas for the session.

On top of that, we prepared a [presentation for participants](https://docs.google.com/presentation/d/1r_3X5VfLgwG4ZG-jlWtPO_uAI9msTbRnYcyQUe__BCM/edit?usp=sharing)
and a simple [script for facilitators](https://drive.google.com/open?id=1Ryav3NGRNGMARyAWs-iLFjU9CmtoxDynRlczi00hGtg) - a step-by-step of what we want to talk about, useful links, etc. I didn't memorise all of it but the fact of having it written down helped to clarify how to structure the day (mainly the introduction) and when to show sponsor decks, explain the Conway's Game of Life rules, etc.

I also posted a few comments on the [Meetup page](http://www.meetup.com/london-software-craftsmanship/events/226148869) to remind the participants about the event and attach a video by [@alexboly](http://twitter.com/alexboly) in which he explains how to get the most out of it.



On the day
--------------------------

We started the day at 7:30 with [@keyvanakbary](http://twitter.com/keyvanakbary), which gave us 1.5h to prepare the event including:

- setting up the tables and chairs
- connecting laptops to the big monitor and the speakers and making sure we can do live coding and video chats
- preparing name tags
- printing out the wifi password

We chose the following constraints:

1. Keep methods no longer than 4 lines
2. Ping-pong TDD
3. No conditionals
4. Silent pair programming
5. Baby steps (3 minutes to check in or revert, after 30 min we switched it to 2 minutes)
6. No tests (+ asking participants to switch to somebody else's machine after 35min)

Essentially all the **constraints were chosen on the day**. That is, we decided the first one just short before 9:00 and then we were selecting the following one while people were pairing, responding to what we observed.

**Keep methods no longer than 4 lines** was more of a warm-up. We just wanted to make sure people can run tests and learn about the Conway's Game of Life.

**Ping-pong TDD** came second. We knew TDD will be used throughout the day so we wanted to remind participants of the steps and also even out on-the-keyboard time within pairs.

**No conditionals** took away one of the most common tools for programmers in order to get them out of their comfort zone.

**Silent pair programming** opened the, what I like to call "memorable" afternoon sessions, taking away something as essential as verbal communication and forcing people to maximise the expressiveness of their code.

**Baby steps** followed as the 5th one. It's not uncommon for programmers to write a simple test that requires to implement everything at once or that gets us stuck. This session was aimed at working on smaller chunks and continuously integrating our code in VCS.

**No tests** closed the day by using the power of contrast built on the 5 TDD-based sessions before. The effect was intensified when people were asked to move to another machine.

Just after the 6th session we had a **video chat** with the group from Valtech in London. We structured it to have 3 people from each group answer a question "what was your favourite session and why?". Being our neighbours, they also invited us to a pub afterwards. As we were about to finish it a group from Santiago in Chile joined our chat, which was a pleasant surprise.

The first mini-retrospective was just a simple conversation between all of us. From the second one on we switched to use a baseball ball where the person that has finished descibing their experiences throws it to somebody else inviting them to talk. The goal here was to keep retros more fun and also to give more people a chance to express their thoughts. For the final retrospective we upgraded to a bigger ball - to symbolically make it stand out ;-)


On the day - afterthoughts
--------------------------

Things that I have gone well:

- meeting my co-facilitator before the event and discussing some organisational ideas
- co-facilitating helped greatly as we could complete each other, generate more ideas and of course eassist more pairs
- creating a presentation for the participants, so that they could reread the constraints any time.
- having that presentation available online (on Google Drive) enabled us to tweak it easily on the day from any laptop and it automatically refreshed on the main monitor
- [appear.in](http://appear.in) was fantastic as a video chat tool because we had many code retreats in the same room which gave it a more global feeling. The fact that a group from Chile spontaneously joined us was fantastic
- printing out [@marcoemrich](http://twitter.com/marcoemrich)'s [picture with the Conway's Game of Life rules](https://github.com/marcoemrich/game-of-life-rules) was a huge help to participants. I saw them used heavily throughout the whole day
- using a ball in a retrospective caused people to smile and helped in evening out the talking time for everybody
- inspired by [Craig Larman](https://en.wikipedia.org/wiki/Craig_Larman) I played music in the breaks between sessions 1-2, 2-3, 4-5 and 5-6. Music was a subconcious signal that the session and the mental effort is over and it's time to relax. It also distinguished one session from another, enforcing many "beginnings" and "ends", which are the most memorable parts of any activity

If I was to change something now, I would have:

- gone to TransferWise a few days before to try connecting to the monitor and speakers. It took us around 45 minutes to get it done - we barely did it on time
- brought in headphones in order to try out the video chat without interrupting people (this ideally would have also been tried out a few days before)
- connected to more code retreats from other countries to stress it's a global event
- spent just a tiny bit more time on explaining the constrains and then always asking a question if they are clear. Possibly I would have asked some leading questions, for example in the Silent Pair Programming session: "how else can you express your intent if you can't talk" or "if you don't understand your partner's test, what options do you have to make it clear" or maybe "while you are writing your code silently, how can you make it easier for your partner to follow". Then in the retrospective, participants would have tried to answer these questions.
- tried harder to remember when each session started ;-)

I would have considered changing:

- using slightly more session-dependent, targetted retrospective questions (like in [this facilitator's tutorial](https://drive.google.com/folderview?id=0B5c0gS3XXAGfa0xGdE1qNW1NX1k&usp=drive_web)) or perhaps even 2-3 different retro formats to keep things fresh
- doing a TDD demo (in fact I had prepared one but skipped it because we were slightly behind the time schedule)



After the event
--------------------------

There were a few tasks I brought home such us:

- thanking everybody for coming and providing links to the [GDCR timeline](http://gdcr.coderetreat.org/timeline-2015.html) and the [Twitter #gdcr15 hashtag](https://twitter.com/hashtag/gdcr15?vertical=default&src=hash) in the Meetup comments, in order to enforce the feeling of being part of a global event
- sending out an email with the vouchers and discounts for the participants
- publishing the pictures from the day on [the Meetup page](http://www.meetup.com/london-software-craftsmanship/photos/26550627)


Summary
--------------------------

The Global Day of Code Retreat 2015 was a great learning experience for me. Thank you:

- all the participants for making this day with us
- [@keyvanakbary](http://twitter.com/keyvanakbary) - for facilitating it together and keeping it so fun
- [@Singsalad](http://twitter.com/Singsalad) - for the **weeks** of your effort and coordination
- [@gemcfadyen](http://twitter.com/gemcfadyen) - for the encouragement and tips (TDD, retros)
- [@marcoemrich](http://twitter.com/marcoemrich) - for the fantastic facilitator training and the attached notes
- [Software Craftsmanship Krakow](http://www.meetup.com/sc-krk/events/90017372) - for my first ever, inspiring Global Day of Code Retreat 2012
- [@coreyhaines](http://twitter.com/coreyhaines), [@adibolb](http://twitter.com/adibolb), [@alexboly](http://twitter.com/alexboly) and all the people who created and popularised Global Day of Code Retreat

I would be happy to read your feedback below in the comments.
