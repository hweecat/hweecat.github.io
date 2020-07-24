---
layout: post
title: "Parallel and Asynchronous Programming in Python for Data Science"
description: "A self-primer on when to parallel and asynchronous programming in Python for data science projects"
excerpt: "Slow code, as well as connectivity issues, are common bottlenecks in data processing that affect every step of a typical data science workflow — be it for event-driven I/O operations or computation-driven workloads. Through real-life analogies based on my experience in a young data science team getting started with real-world data, I will be exploring the use of parallel and asynchronous programming in Python to speed up your data processing pipelines so that you could focus more on getting value out of your data."
tags: til python
---
---

## Background

My very first meetup talk was a gentle introduction to parallel processing for data science at the Python User Group Singapore meetup last August. It was meant as a practice talk for my first conference talk on using parallel processing and just-in-time (JIT) compilation for data science at [Women Who Code CONNECT Asia 2019](https://hweecat.github.io/talk_how-to-make-your-data-processing-faster/) a few days later. These first two talks were based on my writeup on [accelerating batch processing of images using concurrent.futures and numba](https://hweecat.github.io/accelerating-batch-processing/), which was effectively an "angst" post to milk my money's worth of wasting time on image processing.

After the warm reception and feedback from the audience who asked interesting questions about speeding up I/O operations using concurrent.futures, it seemed worthwhile to delve further into the use of parallel and asynchronous programming in Python for data applications. While on a speaking break, I rewatched my talk recordings (it feels weird picking out your glaring mistakes while watching yourself speak, I swear) and got down to research further on parallel programming + asynchronous programming + concurrency + concurrent.futures for data applications. When I finally felt ready to plan out the structure of the improved talk I had in mind, I got down to work on my talk abstract and submitted the talk proposal to multiple conferences for the year 2020.

Alas, 2020 wasn't really a good year for conferences. I expected it to be tough, but I didn't expect my conference speaking goals to be wrecked by a global pandemic.

For the benefit of those who couldn't be there physically for my talk, here it is in written form: parallel and asynchronous programming in Python for data science.

## Abstract

In a data science project, one of the biggest bottlenecks (in terms of time) is the constant wait for the data processing code to finish executing. Slow code, as well as connectivity issues, are common bottlenecks in data processing that affect every step of a typical data science workflow — be it for event-driven I/O operations or computation-driven workloads.

Through real-life analogies based on my experience in a young data science team getting started with real-world data, I will be exploring the use of parallel and asynchronous programming in Python to speed up your data processing pipelines so that you could focus more on getting value out of your data.

## The Data Science Process

A data science project consists of these 4 phases:

1. Data Collection
2. Data Processing
3. Model Training
4. Model Deployment

I collect the raw data, process the data, use the data to train the data model, and deploy the model when it is ready. Seems pretty straightforward, right?

## Bottlenecks in a data science project

Turns out, there's quite a fair bit of bottlenecks in a data science project.


According to a 2019 survey by O'Reilly on AI Adoption, enterprises with mature AI practices cited "Lack of data or data quality issues" as the main bottleneck holding back further adoption of AI technologies. Even with advances in building robust models in recent years, the reality is that noisy or incomplete data remain the biggest hurdles to designing effective end-to-end data science projects. Hence, it is often necessary and even crucial to perform data preprocessing on the data before any analysis or or training of analytics models could be performed.

Data cleaning is usually required to improve the quality of data, but they consume a large amount of time spent on most data science projects. For real-life enterprise data science projects where domain knowledge is an integral part of the data but are often not encoded in the data, data quality issues are often more complex and require extensive data preprocessing and cleaning with domain knowledge inputs before models could be trained.

A common adage is that a typical data science workflow follows the 80:20 Pareto principle - 80% on data preparation and cleaning (data preprocessing), and 20% on data mining and model building. In real-life data science projects where data quality issues are often more complex, it's closer to 90:10 - 90% on gathering requirements and data preprocessing with consultation with domain experts, and 10% on data mining and model building. Data cleaning can be labour intensive; even if the data munging process could be automated, slow data processing codes also contribute to significant bottlenecks in data science projects in terms of time.

## Data Processing in Python

Data processing speeds (especially for-loops) in Python are said to be infamously slow compared with C. This is because Python runs on the interpreter and is not a compiled language! Why is this so?

Let's illustrate the possible data processing techniques that could be used in Python with an example - calculate the square of each number in from 0 to 99 and return the output as a list.

### For-loops in Python

```python

    a_list = []
    for i in range(100):
        a_list.append(i*i)
```

To perform the operation with a Python for-loop, we initialize an empty list and append each result to the list during each iteration. This involves 

Another key point to consider in the process time: Python for-loops run on the interpreter, not compiled (in contrast, for-loops in C are compiled). The Python interpreter adds significant overhead over multiple iterations as it has to translate the code at runtime, in contrast with C programs that are compiled into native code at compile time and executed at runtime.

### List Comprehensions

Next, we look at list comprehensions and how to implement the same data processing algorithm using list comprehensions.

```python

    a_list = [i*i for i in range(100)]
```

List comprehensions in Python are optimized for the Python interpreter to recognize predictable patterns during looping. Hence, it does not need to load the attribute of the list and call it as a function at each iteration.

### Pandas

Pandas 