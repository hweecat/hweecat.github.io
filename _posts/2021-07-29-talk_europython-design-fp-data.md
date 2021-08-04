---
layout: post
title: "Talk: Designing Functional Data Pipelines for Reproducibility and Maintainability (EuroPython 2021)"
description: "Quick speaker notes + EuroPython 2021 talk reflection"
excerpt: "I designed this talk as a momentum-driven, content-packed, visually engaging talk that is a cumulation of my experiences in designing data pipelines at scale and learning functional programming. Thinking that it would make for a great comeback talk to demonstrate and reinforce my learnings (and a taster for my ongoing series on learning functional programming and Scala), I pictured myself engaging the audience with illustrations of functional programming concepts and design patterns for data pipelines. Murphy's Law had other ideas though - if not for a huge stroke of luck and some help, I can't imagine what it spells for my reputation as a tech speaker."
tags: talks
---
---
Where: [EuroPython 2021](https://ep2021.europython.eu/)

When: 29 July 2021

Location: Online

Resources used:
1. [Functional Programming in Scala by Paul Chiusano and Rúnar Bjarnason](https://www.amazon.com/Functional-Programming-Scala-Paul-Chiusano/dp/1617290653)
2. [Functional Programming Simplified by Alvin Alexander](https://fpsimplified.com/)
3. [Functional Python Programming by Steven F. Lott, 2nd Edition](https://www.amazon.com/Functional-Python-Programming-programming-built-dp-1788627067/dp/1788627067/ref=dp_ob_title_bk)
4. [Built-in Functions - Python 3.9.6 Documentation](https://docs.python.org/3/library/functions.html#map)

## Recap

A recap of what I went through during my talk:

1. Challenges in designing data pipelines at scale
	- Reproducibility
        - Challenges in testing due to dependencies in data pipeline design
        - Challenges in debugging parallel/concurrent code at runtime due to shared states
	- Maintainability
        - How to write readable code that is easy to test and debug in production
        - How to design modular data pipelines for reusability
2. Key Principles of Functional Programming
	- Pure functions and avoid side effects
        - Deep-dive into "pure function"
        - What is a "side effect"
	- Immutability
        - Key Implication: Ease of writing parallel/concurrent programs
    - Referential transparency
        - What is an "idempotent function"
        - Equational reasoning
3. "Control Flow" in Functional Programming
	- Higher-order functions
        - Functions as "first-class citizens"
        - Anonymous functions (or Lambda expressions in Python)
        - map/filter/reduce vs for-loops
	- Recursions as a form of "functional iteration"
        - Recursion vs Iteration
        - Tail-call optimization
4. Functional design patterns for data pipeline design in Python
	- Built-in higher order functions in Python
        - map/filter vs list comprehensions
        - How map/filter improves reusability of data transformations
        - Parallel and concurrent programming with map/filter
	- Immutable data structures in Python
        - `tuple` vs `list`
        - `namedtuple` vs `class` vs `dict`
        - How immutable data structures make data pipelines more reproducible
	- Structural pattern matching (PEP 634)
        - PEP 634 and its similarities with Scala
        - match/case expressions vs if/elif/else
        - How structural pattern matching improves maintainability of data pipeline design
	- Recursions in Python
        - Recursion limit and the issue of tail-call optimization in Python
	- Type systems
        - Type checking and type hints in Python
        -  How type checking help in preventing bugs at runtime		
5. Can we write a purely functional data pipeline in Python?
	- "Functional Core, Imperative Shell"
6. Key Takeaways
    - Adopt functional design patterns when designing data pipelines at scale
    - "Functional Core, Imperative Shell" to manage side effects

## Slides

[EuroPython 2021 - Designing Functional Data Pipelines for Reproducibility and Maintainability](https://bit.ly/ep2021-design-fp-data)

## Quick reflection

I designed this talk as a momentum-driven, content-packed, visually engaging talk that is a cumulation of my experiences in designing data pipelines at scale and learning functional programming.

Thinking that it would make for a great comeback talk to demonstrate and reinforce my learnings (and a taster for my ongoing series on learning functional programming and Scala), I pictured myself engaging the audience with illustrations of functional programming concepts and design patterns for data pipelines. In fact, I made the visuals in my talk slides - designed to fit my own mental imagery of these technical concepts.

Murphy's Law had other ideas though - if not for a huge stroke of luck and some help, I can't imagine what it spells for my reputation as a tech speaker.

I was the first speaker for Conference Day 2 in the Parrot (Data Science) Track. I thought, okay - looks like I do have to make sure I can deliver in my talk and hype up the audience.

During speaker rehearsals and pre-talk checks, I made sure to perform the usual tech checks to ensure that the audio and microphone for my wireless buds were working fine with StreamYard. In fact, during the speaker rehearsal I enquired about contingencies in the unfortunate case that technical issues crop up during the actual talk - fearing a repeat of what happened during PyJamas 2020. We laughed it off saying that it's not likely to happen a second time.

Guess what? It almost happened a second time.

As I felt that sitting down while delivering my talk might constrain my voice projection and restrict my momentum-driven (or adrenaline-driven) style of speaking, I decided to give the talk standing up - with piles and piles of books propping up the laptop and myself standing a distance away from the laptop with a presenter.

Towards the second half of my talk, technical issues started cropping up as the audience started complaining about the audio cracking up. Next, I couldn't really hear the technicians when trying to reset the wireless buds connection and my Internet connection went offline.

By the time I managed to get back online with the audio resolved, I only had barely less than 3 minutes left in my timeslot.

The moment I was told that I ran out of time after the technical issues, my heart seriously sank deep. It's not the first time my talk was absolutely derailed due to technical issues, which means that this second incident might cause a serious hit to my reputation as a speaker.

In fact, I felt that my more recent talks were not that well received - which might have negatively impacted my call-for-proposals acceptance rate this year.

I do have a lot more anxiety relating to conference speaking, career progression, performance metrics and all, but I shall leave that in a future post.

While I took some time to mourn the supposed premature death of my speaking career, it turned out that the next talk was...cancelled.

With some time left to go before Day 2 Morning Keynote, Cheuk asked if I would like to continue with my talk. I said yes, took a deep breath and a sip of water, and proceeded to rejoin the StreamYard session.

I picked up where my talk faltered, continued the momentum while I started speaking animatedly about functional design patterns in Python (there are a few, especially in recent years), and managed to complete my talk.

Right after the talk, I noticed that my lips had started to crack a bit and the right side of my mouth was bleeding as my inner right cheek got caught with my metal braces.

I'm not sure if I'm going to be speaking anytime soon until in-person conferences resume. In the meantime, I'll have to keep trying and reflecting on my own conference speaking goals.

### Things that could have been improved

1. Can I just emphasize once again that it's starting to feel very unnerving for me when I can't gauge audience feedback when I'm speaking to the webcam and I don't know whether anyone can actually tolerate whatever I am saying? I'm not sure if they're just saying nice things out of courtesy, or if they really enjoyed my performance.
2. Since I designed my talk to be very content-packed and momentum-driven within 30 minutes (because I seriously cannot stand talking to myself for more than 30 minutes without audience engagement when I'm delivering a technical talk), I could not afford to slow down or leave any room for technical disruptions this time - and it really showed very glaringly when the untimely technical issues struck halfway through my speaking slot. 
3. Time for me to change to a reliable data bundle plan with generous data allowance. My internet connection is clearly failing me.

### Things that went well

1. Did anything *actually go well during the talk*? 
2. Oh yes, there's one - I managed to cover everything that I wanted to cover in my talk, thanks to a twisted stroke of luck (at the expense of another)!