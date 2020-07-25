---
layout: post
title: "Talk: Speed Up Your Data Processing (EuroPython 2020 Edition)"
description: "Quick speaker notes + EuroPython 2020 talk reflection"
excerpt: I originally designed this talk to be interactive and audience-driven, with the pace of the talk driven by casual "coffee shop" banters with the audience. With the COVID-19 pandemic showing no signs of abating, my original plan of making my European speaking debut at Ljubljana was disrupted. I still wanted to make my European speaking debut with the same talk somehow; hence, I submitted the talk proposal for EuroPython 2020 and hoped for the best.
tags: talks
---
---
Where: [EuroPython 2020](https://ep2020.europython.eu/)

When: 23 July 2020

Location: Online

Resources used:
- [Official Python documentation on concurrent.futures](https://docs.python.org/3/library/concurrent.futures.html)
- [Built-in Functions](https://docs.python.org/3/library/functions.html#map)

## Recap

A recap of what I went through during my talk:

1. Bottlenecks in a data science project
2. Challenges in data processing in Python
    - For loops in Python are slow
    - List comprehensions are slightly better
    - Pandas is great for analytics but doesn't quite scale for larger data
    - Spark cluster? Problem of "Small Big Data" + communication overhead across computes (+ communication network analogy)
3. What is parallel processing? What do you mean by asynchronous?
    - Bonus: Introducing the traditional Singaporean breakfast!
    - Sequential vs parallel processing
    - Synchronous vs asynchronous execution
4. When should you go for parallelism?
    - Practical considerations
        - Is your code already optimised?
        - Problem architecture
        - Overhead in parallelism
            - Amdahl's Law - not everything can be parallelized
    - Multithreading vs Multiprocessing
5. Parallel + asynchronous programming for data processing
    - Data processing tends to be more compute-intensive
    - Most data folks use Python -- GIL does not allow parallel thread execution       
    - How to do parallel + asynchronous processing in Python?
        - concurrent.futures module in Python
        - ThreadPoolExecutor vs ProcessPoolExecutor
        - executor.submit() and executor.map() in concurrent.futures
7. Putting Them All Together
    - Case: Network I/O Operations
    - Case: Image Processing
7. Key Takeaways
    - Not all processes can be parallelized
    - Don't use for-loops!

## Slides

[EuroPython 2020 - 23 July 2020 - Speed Up Your Data Processing](https://bit.ly/europython-parallel-async)

## GitHub Repository for Demo

[hweecat/talk_parallel-async-python](https://github.com/hweecat/talk_parallel-async-python)

## Video

Pending processed recording

## Quick reflection

I originally designed this talk to be interactive and audience-driven, with the pace of the talk driven by casual "coffee shop" banters with the audience. With the COVID-19 pandemic showing no signs of abating, my original plan of making my European speaking debut at Ljubljana was disrupted. I still wanted to make my European speaking debut with the same talk somehow; hence, I submitted the talk proposal for EuroPython 2020 and hoped for the best.

To be honest, my heart almost sank when I checked that my talk wasn't part of the list of talks selected by popular vote - in fact, I followed up with another talk proposal when Call for Proposals was called for APAC timeslots. Hence, I came in without much expectation on audience interest (in fact, I didn't promote my own talk that actively this time - I was just happy to be given a chance to speak at EuroPython with an impressive lineup of high-profile Pythonistas!) - even if I did bomb my talk spectacularly and nobody likes my talk, at least I could tell other people that I spoke at EuroPython before. +1 person who enjoys my talk = +1 bonus point to my speaker karma.

Bonus: I added the traditional Singaporean breakfast reference for the non-ASEAN audience - if they don't understand any of the contents in my talk, at least they understand the universal language of food and will have something delicious to "takeaway" from my talk.

### Things that could have been improved

1. Can I just emphasize once again that it feels kinda weird not being able to gauge audience feedback when you're speaking to the webcam and you don't know how many people are actually watching your talk?
2. Without knowing whether the audience is following or enjoys my talk, I found myself attempting to slow down the pace at the beginning so that the audience could follow my talk - and ended up with 5 minutes to cover the Python implementation portion of my talk. Pacing could have been better managed to be more evenly spread out?
3. I was definitely rushing towards the end of my talk, and I think it showed - my friends who watched my talk said that I looked visibly stressed.
4. I somehow feel a bit self-conscious about my speech delivery when speaking to audiences beyond Asia, especially when my talk timeslot is placed after more esteemed speakers with better-received talks. In fact, I stopped actively watching talks at least 1hr before my talk timeslot because I felt "inferior" in comparison as a speaker and that I needed more time to prepare myself mentally for my talk - even though I have delivered similar variations of the talk before. More about that next time.

### Things that went well

1. I managed to cover everything that I wanted to cover in my talk on time - all wthin 30 minutes!
2. A couple of people approached me virtually after the talk to say that they enjoyed my toast and coffee analogies - one of them even wanted to "steal" the analogy!
3. Pretty interesting Q&As and discussion after the talk - a (slight) positive indicator of interest in my talk and also a good opportunity to discuss more about using a systems-based approach in analysing how to speed up parts of data processing pipelines.