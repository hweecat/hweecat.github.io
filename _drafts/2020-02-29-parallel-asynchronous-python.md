---
layout: post
title: "Parallel and Asynchronous Programming in Python for Data Science"
description: "A self-primer on when to parallel and asynchronous programming in Python for data science projects"
excerpt: "Slow code, as well as connectivity issues, are common bottlenecks in data processing that affect every step of a typical data science workflow — be it for event-driven I/O operations or computation-driven workloads. Through real-life analogies based on my experience in a young data science team getting started with real-world data, I will be exploring the use of parallel and asynchronous programming in Python to speed up your data processing pipelines so that you could focus more on getting value out of your data."
tags: til python
---
---

I first delivered a talk on using parallel processing and just-in-time (JIT) compilation for data science at [Women Who Code CONNECT Asia 2019](https://hweecat.github.io/talk_how-to-make-your-data-processing-faster/), which is based on my writeup on [accelerating batch processing of images using concurrent.futures and numba](https://hweecat.github.io/accelerating-batch-processing/). While w

## Abstract

In a data science project, one of the biggest bottlenecks (in terms of time) is the constant wait for the data processing code to finish executing. Slow code, as well as connectivity issues, are common bottlenecks in data processing that affect every step of a typical data science workflow — be it for event-driven I/O operations or computation-driven workloads.

Through real-life analogies based on my experience in a young data science team getting started with real-world data, I will be exploring the use of parallel and asynchronous programming in Python to speed up your data processing pipelines so that you could focus more on getting value out of your data.

## Background

A data science project consists of these 4 phases:

1. Data Collection
2. Data Processing
3. Model Training
4. Model Deployment



