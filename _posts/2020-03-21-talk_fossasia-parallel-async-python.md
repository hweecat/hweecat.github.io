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

[Speed Up Your Data Processing: Parallel and Asynchronous Programming in Python](https://youtu.be/aB6f5KicM2Y)

## Quick reflection

Year 2020 started out bad. Real bad. The COVID-19 pandemic led to a string of cancellations for tech events (including PyCon) and travel restrictions. As a result of travel restrictions and Business Continuity Plans, many speakers were not able to deliver their talks in person at the eleventh hour, participation was greatly reduced by around 90%, and even the FOSSASIA organizers could not make it to the venue in person due to COVID-19 restrictions. Still, the organizers made the decision to proceed with the event with a mix of offline and online talks with live streaming and chats.

The first version of this talk was given as a gentle introduction to parallel processing for data science at the Python User Group Singapore meetup last August. Based on the warm reception and feedback from the audience, I revamped the talk content to include more in-depth points on parallel programming for network I/O operations and multithreading. When crafting the revamped talk, I assumed that the audience has a basic understanding of Python and data processing in data science - for loops, list comprehensions, pandas DataFrames etc.

It does feel a bit weird giving a talk to a room of less than 10 people and a livestream audience of I-have-no-idea-how-many, but I still did my show anyway - complete with loads of animated hand-flailing and coffee analogies.

### Things that could have been improved

1. I may have gone slightly beyond 25 minutes for my talk - but still within schedule!
2. Can I just emphasize that it feels kinda weird not being able to gauge audience feedback when you're speaking to a livestream audience and you don't know how many people are actually watching your talk?
3. Slight technical issues with livestream caused a bit of interruption in the middle.
4. I wish there were a way to engage the livestream audience too, but I guess I'll have to get used to speaking without knowing whether the audience is following or enjoys my talk.
5. I swear I use too many "so......" in my talks until I suspect it's becoming a hindrance to my speaking goals. Time to fix that.

### Things that went well

1. My talk went well without major hiccups and there were more than 5 persons in the room. Considering the greatly reduced physical attendance and social distancing measures, I guess having more than 5 persons in the room isn't too bad.
2. Ben Sadeghi (the really cool Databricks solution architect who spoke after me) likes my talk!
3. Questions! Having people in the audience asking relevant questions is a good indicator of interest and engagement - I like that.