---
layout: post
title: "Learning Scala as a Python Programmer: Higher-Order Functions for Functional Data Pipeline Design"
description: "Fourth post for a series of posts on functional programming for data engineering"
excerpt: "In my previous post on functional programming features for control flow, I provided an overview of function decomposition, and discussed the use of higher-order functions and recursion as a form of functional iteration. In this post, we will explore more on Higher-Order Functions and how they can be used in designing functional data pipelines."
tags: python scala functional-programming
author: ongchinhwee
largeimage: /images/data_pipeline_sketch.png
---
---

## Recap

In my previous post on [functional programming features for "control flow"](https://hweecat.github.io/learning-scala-functional-programming-features-control-flow), I provided an overview of function decomposition, and discussed the use of higher-order functions and recursion as a form of "functional iteration".

In this post, we will explore more on Higher-Order Functions and how they can be used in designing functional data pipelines.

Before that, let's start with how a typical data pipeline looks like.

## Data Processing and the Data Pipeline Design Pattern

A classic approach to data processing is to write a program that uses the **data pipeline** design pattern.

![alt text](https://hweecat.github.io/images/data_pipeline_sketch.png "sketch of data pipeline design pattern")
Data Pipeline Design Pattern

In a typical data pipeline, we read data from a source, transform the data in some desired way, and collect the output as new data. This is what is commonly known as the "extract, transform, load" (ETL) process.

- **Extract**: In the data extraction phase, data is extracted from the source system(s) and validated for correctness.
- **Transform**: In the data transformation phase, a series of functions are applied to the extracted data in order to prepare it for loading to the target data store.
- **Load**: In the data load phase, the data is loaded into the target data store - it could be a flat file (such as CSV or Parquet) or data warehouse.

## Higher-order Functions for Data Transformations

A simplified sketch of a typical ETL process from database source to flat file in S3 bucket is shown below:

![alt text](https://hweecat.github.io/images/etl_sketch.png "sketch of etl process")
Sketch of an ETL Process

While the data extraction and data load phases depend on the states of the source and target data store outside the program, the data transformation phase depends on the input data and the function applied to the data within the program itself. Hence, data transformation can be naturally expressed as a functional operation composed with a series of functions  - also known as **function composition**.

For programming languages that support functions as first-class objects, function composition can be expressed in the form of a higher-order function. While we can write our own higher-order functions, there are a few useful built-in higher-order functions that are commonly used in data transformations:

- `map`
- `filter`
- `reduce`

The focus of this post is to explore these built-in higher-order functions and discuss how they can be used in designing functional data pipelines.

### `map`

The `map` function accepts a function as input, applies the function to every element in a collection of values, and returns a new collection of function output values.

![alt text](https://hweecat.github.io/images/map_function_sketch.png "sketch of map function")
Sketch of `map` function

For example, when we map a collection of shapes with an `addSmile` function, 

A detailed discussion on the `map` implementation in Python and Scala can be found in my previous post.

### `filter`

The `filter` function accepts a function condition as input, filters out elements in a collection based on the input function condition, and returns the filtered elements as a new collection.

![alt text](https://hweecat.github.io/images/filter_function_sketch.png "sketch of filter function")
Sketch of `filter` function

For example, when we map a collection of shapes with an `addSmile` function.

### `reduce`

![alt text](https://hweecat.github.io/images/reduce_function_sketch.png "sketch of reduce function")
Sketch of `reduce` function

### `flatMap` vs `map`


## Comprehensions as Syntactic Sugar


## What's Next