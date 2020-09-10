---
layout: post
title: "Talk: Speed Up Your Data Processing: Parallel and Asynchronous Programming in Data Science (PyCon TW 2020 Edition)"
description: "Quick speaker notes + PyCon Taiwan 2020 talk reflection"
excerpt: Speaking at PyCon Taiwan has been one of my key priorities in year 2020 even before the pandemic (another of my key prioriies was to speak at a conference outside of Asia). The fact that there will be an offline audience at the other end of the remote call is also a "pull" factor in my decision to speak at PyCon Taiwan this year - I really miss being able to see live audience responses at a physical conference!
tags: talks
---
---
Where: [PyCon Taiwan 2020](https://tw.pycon.org/2020/)

When: 6 September 2020

Location: NCKU, Tainan / Remote

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

[PyCon Taiwan 2020 - 6 September 2020 - Speed Up Your Data Processing - Parallel and Asynchronous Programming in Data Science](https://bit.ly/pycontw-parallel-async)

## GitHub Repository for Demo

[hweecat/talk_parallel-async-python](https://github.com/hweecat/talk_parallel-async-python)

## Video

Pending processed recording

## Quick reflection

Speaking at PyCon Taiwan has been one of my key priorities in year 2020 even before the pandemic (another of my key prioriies was to speak at a conference outside of Asia). Taiwan was where I made my international debut on the conference-speaking circuit, and I initially planned to travel in Taiwan for a week in between PyCon Taiwan and Open Up Global Summit and speak at both conferences. Alas, things didn't go according to plan:

1. Even though PyCon Taiwan 2020 could proceed as an offline conference, flying in to Taiwan as a speaker is not an option due to the 14-day quarantine period. So, I had to present remotely instead.
2. The pandemic moved Open Up Global Summit online, and it is not logistically possible for me to prepare for two different talks within one week from each other without compromising on quality (I do have a full-time role as a data engineer after all). Moreover, being stuck in Singapore (as opposed to travelling alone in Taiwan) means that I do not have as much leeway and flexibility in terms of schedule during the weekends due to *the much-dreaded family obligations*.
3. Presenting remotely does take a toll on my mental health, and not having an actual break in between means that I take longer to recover and prepare for the next remote talk.

Since speaking at Python conferences is my top priority for this year, I decided to focus my efforts on PyCon Taiwan this time. The fact that there will be an offline audience at the other end of the remote call is also a "pull" factor in my decision to speak at PyCon Taiwan this year - I really miss being able to see live audience responses at a physical conference! The organizing team also provided YouTube livestreams for the talks so that attendees who are not physically in Tainan would be able to watch the talks, and some of the in-person talks are really interesting. I do feel a bit sad (?) missing out on in-person interactions with the Python community in Taiwan though - time to start thinking about next year's talk proposal!

### Things that could have been improved

1. I tried to gauge the audience at the start of the talk via the livestream that I was watching on my phone, but it turns out I wasn't able to see their live response during the talk since I could only focus on my slides on Google Meet while looking at the webcam. One more reason to seriously consider having a second screen for productivity.
2. Some hiccups with the audio during Q&A which caused me to be unable to hear the questions clearly, which affected my Q&A response somewhat.

### Things that went well

1. Pacing was good this time and I was already wrapping up the talk with 5 minutes to spare - which leaves enough time for Q&A!
2. Pretty interesting Q&A after the talk about multithreading in Python and the effect of GIL on its practical implementation.
3. I really like how I could see the live audience reactions during Q&A!