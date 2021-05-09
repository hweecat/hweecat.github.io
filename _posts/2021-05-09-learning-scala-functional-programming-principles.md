---
layout: post
title: "Learning Scala as a Python Programmer: Key Principles of Functional Programming"
description: "Second post for a series of posts on functional programming for data engineering"
excerpt: "In my previous post on my motivations for learning Scala, I stated that one of my key reasons for learning Scala for data engineering is due to the programming language being primarily designed for functional programming. Before we dive into the details of writing functional programs, it is important for us to understand the key principles of functional programming and how these programming principles are useful when designing reproducible data pipelines at scale."
tags: python scala functional-programming
---
---

## Recap

In my previous post on [my motivations for learning Scala](https://hweecat.github.io/learning-scala-motivations), I stated that one of my key reasons for learning Scala for data engineering is due to the programming language being primarily designed for functional programming.

Before we dive into the details of writing functional programs, it is important for us to understand the key principles of functional programming and how these programming principles are useful when designing reproducible data pipelines at scale.

In this post, I introduce:

1. What is Functional Programming
2. Key principles of Functional Programming and their implications on data pipeline design

## What is Functional Programming

Functional programming is a **declarative** style of programming that emphasizes writing software using **only**:

1. Pure functions; and
2. Immutable values.

To put it simply, functional programmers see their code as mathematical functions - and combinations of functions as equations with defined inputs and outputs.

The concept of pure functions is the *core* of Functional Programming, and has important implications on how functional design principles could be used in designing data applications at scale. For now, here's a simplified definition of "pure function":

1. The output of a pure function depends only on its **input parameters** and its **internal algorithm** (i.e. the "black box" where the input parameters are fed into).

2. A pure function has **no side effects**; it does not have any read/write interactions with the outside world.

3. As a consequence of the above two statements, if a pure function is called with an input parameter *x* infinite number of times, **it will always return the same result *y*** - regardless of any state change of an internal or external process.

### Declarative vs Imperative Programming

In the **imperative programming** paradigm, code is viewed as statements that changes a program's state. An imperative program consists of sequences of statements written as explicit instructions to the computer on how the program operates to change its state.

*Procedural and object-oriented programming* paradigms are extensions of imperative programming to improve maintainability of imperative programs by separating programs into smaller components. Procedural programming focuses on breaking down a program into procedures (also known as subroutines or functions), while object-oriented programming focuses on breaking down a program into objects with state (data) and behavior (code).

While procedural and object-oriented programming allow programs to be expressed in procedures that are easier for a programmer to understand without necessarily looking into the details, the complete program is still imperative since the order of execution for the statements (also known as **control flow**) affects how the program state is being changed.

In contrast with imperative programming, the **declarative programming** paradigm expresses the computation logic of a program without explicitly describing the steps to achieve them in sequence.

*Functional programming* is characterised by a declarative programming style, with computations performed through evaluation of expressions as function application and encapsulation of state mutation over control flow. This programming paradigm enables the programmer to write self-contained reusable and testable programs without additional mock objects and interfaces.

## Key Principles of Functional Programming

The key principles of functional programming are:

1. Pure functions and avoid side effects
2. Immutability
3. Referential transparency

### Pure functions and avoid side effects

When we look at a mathematical function ![\[y=f(x)\]](https://latex.codecogs.com/svg.latex?\inline&space;y=f(x)), we expect the function *f* to do nothing else other than computing the result *y* given its input *x*.

In other words, a **pure** function has no observable effect on the program execution besides returning a result (which is its main effect).

A function with **side effects** changes state outside the local function scope. Examples of side effects include:

- modifying a variable or data structure in place
- modifying a global state
- performing any I/O operation (reading from or writing to a file/database, printing to console or reading user input etc.)
- throwing an exception with an error

To illustrate the concept of pure function and its key implications, let's use an oven as an example:

![alt text](https://hweecat.github.io/images/pizza_pure_function.jpg "illustration of pure function using oven and pizza")
Pure Function - illustrated using oven and pizza

To bake a thin-crust Hawaiian pizza (sorry pizza purists), we need pizza crust and toppings, with the oven temperature set at 160 degree Celsius for 10 minutes. The inputs to the oven-baking function are:

- pizza crust type (thin-crust)
- list of toppings (cheese, tomato, ham, pineapple chutney)
- oven temperature (in degree Celsius)
- baking time (in minutes)

If we assume that the oven-baking operation is a pure function, we assume that the output of the operation *only* depends on the inputs and the internal algoithm of the oven-baking operation. We do not expect any side effects, such as the oven-baking operation burning down the kitchen.

Consequently, we expect the oven to return a perfectly-baked thin-crust Hawaiian pizza *every single time regardless of how many times we perform the operation* given the inputs without changing the state outside the oven. We do not expect the oven to return a cream-based pizza or a burnt pizza given the function input.

In more formal terminology, we expect a **pure function** (the oven-baking operation) to be:

1. *deterministic* and *idempotent* , and
2. without *side effects*.

In reality, we might sometimes open the oven door to check on the oven-baking operation. (I/O operation)

We might decide to shorten the baking time by turning the timer on the oven, or add more cheese to the pizza toppings. (modifying a variable in place)

The oven might heat up its surroundings, increasing the temperature of its external environment. (modifying a global state)

The oven might either get too hot or suffer a short circuit, affecting the successful completion of the oven-baking operation. (throwing an exception with an error)

These effects resulting from the oven-baking operation cause changes in state outside the oven besides the thin-crust Hawaiian pizza, hence making the oven-baking operation an **impure** function with side effects.

### Immutability

**Immutability** means that once a value is assigned to a variable, the state of the variable *cannot be changed*.

The concept of immutability is important in Functional Programming, as it ensures that the function has a disciplined state and does not change other variables outside the function scope. Instead of modifying the value of a variable in place, state changes are managed by creating another instance without affecting the state of the original variable.

The use of immutable variables also ensures that the function is **pure**, as it prevents the side effect of state change after a value is assigned to an immutable variable.

A key implication of immutability is the **ease of writing parallel/concurrent programs** in Functional Programming.

In imperative programming, mutability of states often complicates reasoning about distributed states and concurrent execution, as it is immensely difficult to keep track of shared state changes across threads, cores and processors without running into race conditions. In concurrent operations, data race could arise when two threads perform conflicting operations (with one of them being a write operation) on the same memory location at the same time.

As Python is primarily designed as an object-oriented programming language, its imperative design patterns lead to complications in managing concurrent access to shared variables that are mutable by default - hence the need for a Global Interpreter Lock (GIL) to lock threads and prevent data race.

Immutability in functional programming simplifies the implementation of concurrency and provides powerful ways of building consistent and concurrent programs, as the use of immutable shared states leads to elimination of race conditions - making concurrent programming less problematic compared with the imperative approach.

### Referential transparency

An important property resulting from the use of pure functions is **referential transparency**, which is intricately linked to the ability for **equational reasoning** of programs.

In the book *Functional Programming in Scala* by Paul Chiusano and Rúnar Bjarnason, referential transparency is formally defined as follows: 

> An expression `e` is *referentially transparent* if, for all programs `p`, all occurrences of `e` in `p` can be replaced by the result of evaluating `e` without affecting the meaning of `p`.

In other words, referential transparency is a property of expressions (not just functions) such that an expression can be substituted by its equivalent result without affecting the program logic for all programs.

The absence of side effects is a necessary, but not sufficient condition for referential transparency. The expression also has to be **deterministic** and **idempotent** to ensure the equivalence between the expression and its evaluated result.

A function is **deterministic** if it will always return the same output given the same input.

A function is **idempotent** if it can be applied multiple times without changing the result beyond its initial application. Examples of idempotent functions are the identity function, absolute value function and constant functions.

The sufficient conditions for referential transparency can be illustrated by the following analogy:

What if the oven breaks down over time even without external interference, causing the pizza to not be as well baked as before? There might not be observable side effects, but the output returned from the oven-baking operation is no longer the same as previous outputs given the same input. This makes the oven-baking operation non-deterministic since the result depends on when the operation is evaluated, breaking the property of referential transparency.

A key consequent of the property of referential transparency is that it enables **equational reasoning** of programs. The expression can be replaced with its equivalent result, and computation can be performed by substituting *"equals for equals"* without worrying about evaluation order or program state - similar to evaluating an algebraic expression in mathematics.

This mode of reasoning about program evaluation, called the *substitution model*, is simpler to reason about since the effects of evaluation are purely local and do not require sequential reasoning of state updates to understand the code. Even if there were any bugs in the function during the development process, the ease of reasoning makes debugging easier in functional programming compared with imperative programming.

When designing reproducible data pipelines at scale, having referential transparency in the code provides the following benefits:

1. Idempotency of functions assures the programmer that the data transformation functions in the program are **reproducible** beyond the initial application.
2. It enables the programmer to express code in more concise and readable functions and values, improving **readability** when coding.
3. It allows the programmer to focus on debugging within the function scope without worrying about state changes outside the function scope, improving **maintainability** of core transformations within a data pipeline.

## What's next: Functional Programming for Data Pipeline Design

In this post, we learn about:

1. Functional programming and how it differs from imperative programming
2. Concept of pure functions
3. Key principles of functional programming and their implications on data pipeline design

In my upcoming post, I will dive into some features of functional programming and how to implement them in designing functional data pipelines.

## References

1. [Functional Programming in Scala by Paul Chiusano and Rúnar Bjarnason](https://www.amazon.com/Functional-Programming-Scala-Paul-Chiusano/dp/1617290653)
2. [Functional Programming Simplified by Alvin Alexander](https://fpsimplified.com/)
3. [Mutability - Functional Programming in OCaml](https://www.cs.cornell.edu/courses/cs3110/2021sp/textbook/intro/mutability.html)
4. [programming languages - What is a side effect? - Software Engineering Stack Exchange](https://softwareengineering.stackexchange.com/questions/40297/what-is-a-side-effect)
5. [functional programming - Is Equational Reasoning an application of Referential Transparency? - Computer Science Stack Exchange](https://cs.stackexchange.com/questions/19297/is-equational-reasoning-an-application-of-referential-transparency)