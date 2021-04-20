---
layout: post
title: "Learning Scala as a Python Programmer: Motivations"
description: "First post for an upcoming series of posts on functional programming for data engineering"
excerpt: "One of my tech goals in 2021 is to learn Scala. My key reason for learning Scala is to learn Functional Programming for data engineering. The question is: Why go through the trouble of learning Scala if Functional Programming is supported in Python?"
tags: python scala reflection
---
---

## Motivations for learning Scala

One of my tech goals in 2021 is to learn Scala. My key reason for learning Scala is to learn Functional Programming for data engineering.

The question is: Why go through the trouble of learning Scala if Functional Programming is supported in Python?

### How I learn different programming paradigms

As a language purist who believes in using tools for their intended purposes, I believe that the best way to learn a new programming paradigm (whether it is Object-Oriented Programming or Functional Programming) in depth is to learn a suitable programming language that is:

1. Designed primarily for the target programming paradigm (not as an afterthought)
2. Similar in syntax and code patterns to a programming language that you are already familiar with

The reason why point no. 2 is important is so that the focus would be more on learning the programming paradigm without fretting way too much on the syntax and code patterns.

For example, I learnt Object-Oriented Programming by re-acquainting with C and gradually transitioning to C++ through learning object-oriented concepts such as classes, inheritance and polymorphism. This language transition helped in speeding up the process of learning Python, which is designed to be primarily an object-oriented programming language although the language supports multiple programming paradigms.

### Why is Python not ideal for learning functional data engineering

While exploring parallel programming in Python for data science (and I highly recommend you watch [my PyData Global 2020 talk](https://youtu.be/E9sv2B3Bb20) for a vivid explanation of parallelism), I learnt about functional programming in Python through `map` and `itertools`. It surprised me how intuitively I could relate functional programming to mathematical functions that make sense, and how I am already subconsciously using some functional programming concepts in visualizing my data flows.

Since then, I started diving deeper into different programming paradigms but felt that I wasn't diving sufficiently deep enough into the functional programming paradigm with Python.

1. Python is primarily an object-oriented programming language.

    While functions are first-class objects in Python, the code patterns of the builtins and the Python Standard Library are built around classes and objects. This makes Python primarily designed to encourage object-oriented and imperative design patterns rather than the functional paradigm, even though it is a multi-paradigm programing language that provides developers with some level of flexibility in using their preferred coding pattern.

2. Parallel programming is not truly concurrent in Python due to Python internals design

    The object-oriented design of Python and its builtins also leads to complications in parallel programming in Python, whereby the problem of breaking down a sequential program into parallel chunks implies the need to manage concurrency to prevent concurrent access to a shared variable (hence the need for a Global Interpreter Lock in CPython).

    As a data professional who deals with data volumes that at least requires some level of parallelism, having to spend precious developer hours figuring out which parts of a sequential program can be refactored for parallelism and consistency is a major source of frustration and angst. Having the intuition to break programs down into smaller independent functions (I/O and non-I/O) do not make the process of refactoring for optimal parallelism any easier.

I still love Python for its comprehensive data ecosystem and the friends I made from the community, and I am still actively using Python in my personal and work projects.

However, the demands for scalability and reproducibility of data processing pipelines at a larger scale requires heavy-lifting by parallel or even distributed processing, as well as a programming paradigm that supports that heavy-lifting while allowing data professionals to be productive in designing data solutions that they are confident of in producing the same result for the same data input.

### Why learn Scala for data engineering

There might be various reasons why developers choose to learn Scala. For some, it could be due to web programming. In recent years, a popular reason for learning Scala is for Big Data.

Here are my reasons for learning Scala for data engineering:

1. Scala is primarily designed for functional programming and object-oriented programming

    Scala is designed to seamlessly integrate the object-oriented programming paradigm of Java and the functional programming paradigm, and aimed to address criticisms of Java.

2. The syntax for Scala shares similarities with C/C++ and Python

    Scala uses curly-brace syntax similar to C/C++, and also encourages indentation for nested logical blocks (e.g function within a class). The slight difference is that Scala uses 2 spaces instead of 4 spaces or tabs (which is the case for Python).

3. Scala is a strong statically-typed language with type inference, which saves trivial keystrokes while maintaining strong typing for function definitions

    Static typing allows bugs to be caught more easily during the development process, hence avoiding bugs in complex applications. As a strong statically-typed language, code written in Scala is checked for type safety at compile time rather than at runtime. Similar to Python, Scala also supports type inference - meaning that the Scala compiler can often infer the types based on different elements of the source code.
    
    What Scala differs from Python in terms of type inference is that type annotations are required in arguments of function definitions (they are optional in Python) to prevent breaking changes to function internals and optimize compile times. While I try to use type annotations as much as possible in Python, they do not affect execution on the Python interpreter. Making type annotations explicit as a default has the potential to save precious developer time on debugging applications that rely on multiple functions while ensuring that the desired data type is returned from a function.

### What's next: my progress in learning Scala as a Python programmer

It has been close to 3 months since I started learning Scala, and it has been an incredibly steep learning curve. While I'm glad that I could rely on my prior experiences with learning programming languages to start becoming productive with Scala, I do understand that the learning curve could have been even steeper for someone who is starting fresh.

I do have to admit that functional programming does get a lot of getting used to, especially when one has gotten used to writing code in procedural and object-oriented programming paradigms. I would like to think of functional programming as math with defined inputs and outputs, while procedural programming is a step-by-step recipe and object-oriented programming is objects with properties. They are different ways of writing code that works, but the thinking behind the process of writing code differs.

It does get very tempting to fall back on comfortable code patterns when the learning gets tough, especially in a multi-paradigm programming language like Python. Hence, I do find myself feeling terribly unproductive at times when getting used to (and being "steered towards") writing code in the functional paradigm. I do love using type annotations in Scala though - they do make debugging much easier during the development process!

In my upcoming post, I will introduce the basic principles of functional programming and relate these principles to reproducible data pipeline designs.