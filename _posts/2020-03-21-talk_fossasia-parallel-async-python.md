---
layout: post
title: "Talk: Exploring Seasonal Insights from Singapore Weather Station Data"
description: "Quick speaker notes on making open weather data more accessible - using Singapore Data.gov.sg APIs as a case study + talk reflection"
excerpt: It started out as a weekend coding exploration of real-time data from the Data.gov.sg APIs, but went on to become something more. 2nd iteration of the talk - given at JuniorDevSG
tags: talks
---
---
Where: [FOSSASIA Summit 2020](https://summit.fossasia.org/)

When: 20 March 2020

Location: Lifelong Learning Institute, Singapore

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
    - Spark cluster? Problem of "Small Big Data" + communication overhead across computes
3. What is parallel processing? What do you mean by asynchronous?
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

## Slides

[FOSSASIA Summit 2020 - 20 Mar 2020 - Speed Up Your Data Processing - Parallel and Asynchronous Programming in Python](https://docs.google.com/presentation/d/1J5_40II5gUeGFZKRHOg6s4oCSGN0Sh_ldMv4rUjH4oo/edit?usp=sharing)

## GitHub Repository for Demo

[hweecat/talk_parallel-async-python](https://github.com/hweecat/talk_parallel-async-python)

## Video

Pending processed video from FOSSASIA team

## Quick reflection

Year 2020 started out bad. Real bad. The COVID-19 pandemic led to a string of cancellations for tech events (including PyCon) and travel restrictions. As a result of travel restrictions and Business Continuity Plans, many speakers were not able to deliver their talks in person at the eleventh hour, participation was greatly reduced by around 90%, and even the FOSSASIA organizers could not make it to the venue in person due to COVID-19 restrictions. Still, the organizers made the decision to proceed with the event with a mix of offline and online talks with live streaming and chats.

The first version of this talk was given as a gentle introduction to parallel processing for data science at the Python User Group Singapore meetup last August. Based on the warm reception and feedback from the audience, I revamped the talk content to include more in-depth points on parallel programming for network I/O operations and multithreading. When crafting the revamped talk, I assumed that the audience has a basic understanding of Python and data processing in data science - for loops, list comprehensions, pandas DataFrames etc.

It does feel a bit weird presenting to a room of less than 10 people and a livestream audience of I-don't-know-how-many, but I still did my show anyway.