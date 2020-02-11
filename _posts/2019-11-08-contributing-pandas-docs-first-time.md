---
layout: post
title: "Contributing to pandas documentation for the first time - and lessons learnt"
description: "A work-in-progress developer log on contributing documentation for a popular open-source project for the first time."
excerpt: To mark my first year as a data engineer, I started thinking "How can I contribute back to the community that enables my work for the past year?" I came across an open issue on documentation for pandas, a popular open-source Python library for data analysis and manipulation, and decided to give it a try. Here's a work-in-progress developer log on the lessons learnt through contributing documentation to an open-source Python library for the first time - and how contributing to open-source projects is not as scary as it might seem to be.
tags: til
---
---

To mark my first year as a data engineer, I started thinking: 

"How can I contribute back to the community that enables my work for the past year?"

I came across an open issue on documentation for pandas, a popular open-source Python library for data analysis and manipulation, and decided to give it a try. Here's a work-in-progress developer log on the lessons learnt through contributing documentation for an open-source Python library for the first time - and how contributing to open-source projects is not as scary as it might seem to be.

## Some background about myself

As a data engineer, I use pandas for data manipulation, cleaning and analysis to extract insights from raw data. To help in my daily work, I refer to the documentation to figure out which methods to use for data manipulation - be it filtering data tables with specified conditions or setting MultiIndex for multidimensional analysis. However, like most developers, I end up finding my answers on StackOverflow instead of the docs.

After a year of being a data engineer (and a year of using pandas), I thought:

"What better way to mark my first year as a data engineer by contributing to something I use?"

### A bit about pandas

Pandas is an open source data analysis and manipulation library written for Python. It uses DataFrames as fundamental high-level building blocks for data analysis, similar to the concept of data panels in R. Currently, pandas is sponsored by NumFOCUS and has over 1,600+ contributors on GitHub.

### Raising my hand for a docs issue

Looking for an issue to work with may seem daunting when you're looking to contribute to a popular open-source project such as pandas - you don't want to be working on an issue that someone else is already working on. I found a docs issue on MultiIndex which was filed by a user who had some confusion between the ``set_levels`` method and the ``set_names`` method for MultiIndex. Since I have been exploring the use of MultiIndex for multidimensional data analysis, this was a good opportunity to learn more about MultiIndex.

But, it's my first time contributing to a popular open-source project. Would it be okay for me to contribute?

After a few days, I raised my hand (virtually) to ask if I could work on the docs for MultiIndex.set_levels. The answer: Yes.

## Getting started with my pull request

Before I start contributing, there are some best practices on open-source contribution that needs to be followed:

1. One branch, one feature - create a branch to work on a specific feature so that others can keep track of what feature you are working on
2. Before you start working on the code/documntation, fork the repo to your Github account and clone the forked repo to your local machine.
3. Never work directly on the master branch - master branch is supposed to be 'production code'.

## Lessons from contributing documentation


### Lesson 1: Read the style guides and contributing guide

For projects written in Python, the most important style guide to follow is PEP 8, which is the “grandfather” of coding style guidelines for Python codes.

(something about PEP8 and PEP257, performing checks before pushing changes to remote)

### Lesson 2: Git for version control is best learnt by doing

We may try learning Git by reading the documentation, but that would be too overwhelming if you're just getting started with learning Git and still trying to figure out how each command affects the branches. Learning through git tutorials is a good start, but working alone is very different from working in an actual project with multiple contributors in the team. In a team with multiple contributors, how you write your git commits and execute git commands on your branches would have an impact on the branches of your team members - if you accidentally mess with the master branch and break production, good luck!

### Lesson 2.1: Learn the difference between `git merge` and `git rebase`

(difference between `git merge` and `git rebase` is very important - choosing which one to use depends on whether you are working in a small project team or a large team of contributors)

(Pro-tip: Marc ((@datapythonista) uses `git fetch upstream && git merge upstream/master to update his branches with new changes in the pandas-dev project)

### Lesson 2.2: For cleaner commit histories, `git rebase -i HEAD~n` and squash

### Lesson 2.3: `git push -f` responsibly

(when you are the only one working on the branch and you accidentally pushed your changes to your remote repo without performing the checks)

### Lesson 3: Documentation is highly valued - and doesn't require coding

(many open-source projects welcome improvements to the documentation, and you don't need to be an expert in coding to contribute to open source)

### Lesson 4: If you face any challenges, feel free to ask for help!

(I've received helpful advice from the maintainers on how to improve my docs, and what to do when I messed up my Git commands. Open source project maintainers are also human and are willing to help first-time contributors make their first contributions to open source!)
