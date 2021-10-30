---
layout: post
title: "Talk: Designing Functional Data Pipelines for Reproducibility and Maintainability (PyData Global 2021)"
description: "Quick speaker notes + PyData Global 2021 talk reflection"
excerpt: "Getting my proposal accepted for PyData Global a second time was a surprise, given the polarising nature of my talk topic on functional programming and my string of disastrous live talks due to technical issues. For my last virtual live talk of the year, I used an upgraded conferencing setup and modified the structure of my talk to include references to functional design patterns in Apache Spark. For the first time in close to a year, the curse of Murphy's Law in virtual live talks is finally broken."
tags: talks
---
---
Where: [PyData Global 2021](https://pydata.org/global2021/schedule/presentation/7/designing-functional-data-pipelines-for-reproducibility-and-maintainability/)

When: 29 October 2021

Location: Online

Resources used:
1. [Functional Programming in Scala by Paul Chiusano and Rúnar Bjarnason](https://www.amazon.com/Functional-Programming-Scala-Paul-Chiusano/dp/1617290653)
2. [Functional Programming Simplified by Alvin Alexander](https://fpsimplified.com/)
3. [Functional Python Programming by Steven F. Lott, 2nd Edition](https://www.amazon.com/Functional-Python-Programming-programming-built-dp-1788627067/dp/1788627067/ref=dp_ob_title_bk)
4. [Built-in Functions - Python 3.9.6 Documentation](https://docs.python.org/3/library/functions.html#map)
5. [RDD Programming Guide](https://spark.apache.org/docs/latest/rdd-programming-guide.html)

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
4. Functional design patterns for data pipeline design
	- Immutable data structures
        - `tuple` vs `list`
        - `namedtuple` vs `class` vs `dict`
        - How immutable data structures make data pipelines more reproducible
    - Built-in higher order functions
        - Transformations: map/filter
            - How map/filter improves reusability of data transformations
            - Parallel and concurrent programming with map/filter
        - Actions / Aggregations: reduce
            - Transformations first, actions last
    - Functional Design Patterns in Apache Spark
        - Resilient Distributed Datasets (RDDs)
        - Transformations and Actions
	- Structural pattern matching (PEP 634)
        - PEP 634 and its similarities with Scala
        - match/case expressions vs if/elif/else
        - How structural pattern matching improves maintainability of data pipeline design
	- Type systems
        - Type checking and type hints in Python
        -  How type checking help in preventing bugs at runtime		
5. Can we write a purely functional data pipeline in Python?
	- "Functional Core, Imperative Shell"
6. Key Takeaways
    - Adopt functional design patterns when designing data pipelines at scale
    - "Functional Core, Imperative Shell" to manage side effects

## Slides

[PyData Global 2021 - Designing Functional Data Pipelines for Reproducibility and Maintainability](https://bit.ly/pg2021-design-fp-data)

## Video

[PyData Global 2021 - Designing Functional Data Pipelines for Reproducibility and Maintainability (Zoom recording)](https://bit.ly/pg2021-design-fp-data-video)

## Quick reflection

Getting my proposal accepted for PyData Global a second time was a surprise, given the polarising nature of my talk topic on functional programming and my string of disastrous live talks due to technical issues. 

For my last virtual live talk of the year, I used an upgraded conferencing setup and modified the structure of my talk (first presented at EuroPython 2021) to include references to functional design patterns in Apache Spark.

For the first time in close to a year, the curse of Murphy's Law in virtual live talks has finally been broken.

I bought a Logitech C920 Pro HD Webcam for better-quality video conferencing, and upsized my mobile plan from a 24-month contract plan with 10GB data bundle to a more affordable 12-month SIM-only plan with 60GB data bundle so that I can comfortably tether using mobile hotspot during my talk without getting worried about exceeding the data usage cap. The microphone from the Logitech C920 was a significant improvement from the Samsung Galaxy Buds I had been relying on for my past talks - the voice was louder and clearer.

Linking `map`/`filter` with Transformations and `reduce` with Actions in Apache Spark is a key insight I realised when learning and working with Apache Spark and functional programming in Scala. The fact that Resilient Distributed Datasets (RDDs) in Apache Spark is immutable and read-only links back to the functional design pattern of using immutable data structures for parallel operations.

As the PyData audience is likely to be familiar with Apache Spark, I decided to add this particular reference to bring across this message:

    If you have been using Apache Spark for distributed processing, you are probably using functional programming.

With that particular reference, I changed the structure of my talk for the functional design patterns section - from immutable data structures to map/filter/reduce, then a parallel with Apache Spark in the form of RDDs.

With that, I might have made my talk flow more logically and made my message clearer: We should adopt functional design patterns into our data pipelines when designing for scale - and we have plenty to learn about that beyond the Python / PyData ecosystem.

### Things that could have been improved

1. Can I just emphasize once again that I experience a lot of speaker anxiety when I can't gauge audience feedback while speaking to the webcam? It's definitely showing up a lot in my virtual live talks.
2. I choked pretty badly with the longer technical phrases, which resulted in my intontation becoming really clumsy.
3. With the "5 more minutes" interruption towards the end, I was pretty much panicking internally which made the talk even faster. Thankfully (or not), i was already towards the end of my talk.
4. I got really burnt out by the end of my talk until I wasn't able to put my mind into watching the talks in the program for Day 2, because I was really worried that I messed up my talk badly enough and might not be able to speak at another conference again. Once again, this is related to my speaker anxiety that might require more time to reconcile with.

### Things that went well

1. I managed to cover everything that I wanted to cover in my talk on time - all within 30 minutes! (Then again, it might also be me rushing a lot and judicially leaving out more details.)
2. At least 6 - 8 people said nice things about my talk and how I described the concepts of functional programming in relation to data pipeline development on Zoom/Twitter/Gather, so I guess that's an overall win.