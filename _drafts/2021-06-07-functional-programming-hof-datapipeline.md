---
layout: post
title: "Learning Scala as a Python Programmer: Higher-Order Functions for Functional Data Pipeline Design"
description: "Fourth post for a series of posts on functional programming for data engineering"
excerpt: "In my previous post on functional programming features for control flow, I provided an overview of function decomposition, and discussed the use of higher-order functions and recursion as a form of functional iteration. In this post, we will explore more on Higher-Order Functions and how they can be used in designing functional data pipelines."
tags: python scala functional-programming
author: ongchinhwee
largeimage: /images/function_composition.jpg
---
---

## Recap

In my previous post on [functional programming features for "control flow"](https://hweecat.github.io/learning-scala-functional-programming-features-control-flow), I provided an overview of function decomposition, and discussed the use of higher-order functions and recursion as a form of "functional iteration".

In this post, we will explore more on Higher-Order Functions and how they can be used in designing functional data pipelines.

Before that, let's start with how a typical data pipeline looks like.

## Data Transformation and the Pipeline Design Pattern

In a typical data pipeline, we read data from a source, transform the data in some desired way, and collect the output as new data. This is what is commonly known as the "extract, transform, load" (ETL) process.

- **Extract**: In the data extraction phase, data is extracted from the source system(s) and validated for correctness.
- **Transform**: In the data transformation phase, a series of functions are applied to the extracted data in order to prepare it for loading to the target data store.
- **Load**: In the data load phase, the data is loaded into the target data store - it could be a delimited flat file or a data warehouse.


## Why For-Loops are Not Ideal in Data Pipelines


## Higher-order Functions for Data Transformations


### `map`


### `filter`


### `reduce`


### `flatMap` vs `map`


## Comprehensions as Syntactic Sugar


## What's Next