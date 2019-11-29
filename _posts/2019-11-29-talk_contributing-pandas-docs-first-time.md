---
layout: post
title: "Talk: Contributing to pandas documentation for the first time - lessons from open source"
description: "Quick speaker notes on lessons learnt through contributing to pandas for the first time + talk reflection"
excerpt: I use pandas daily, maybe even hourly. I spend time reading the docs, but end up finding my answers on StackOverflow. What better way to mark my first year as a data engineer by contributing to the docs for pandas?
---
---
Where: [Women Who Code Singapore TalksDev #5](https://www.meetup.com/Women-Who-Code-Singapore/events/266037585/)

When: 29 November 2019

Location: SP Digital

Resources used:
- [Contributing to pandas](https://pandas.pydata.org/pandas-docs/stable/development/contributing.html)
- [Pro Git, 2nd Edition](https://git-scm.com/ebook)
- [The original issue with MultiIndex.set_levels](https://hweecat.github.io/accelerating-batch-processing)

## Recap

A recap of what I went through during my talk:

1. How it all started
    - Why contribute to pandas?
    - Raising my hand for a docs issue
2. Some rules in open-source contribution
    - Don't be a code git - many people are contributing
    - Step 0: Fork the project repo before pulling to local
    - One branch, one feature/bug
    - Never make changes on master branch
3. Making my first pull request
    - Isolated dev environment
    - Commit changes to local feature branch
    - Push changes to remote feature branch
    - Tips before you make that pull request
4. Feedback from maintainers
    - Don't expect your first pull request to be perfect
    - The value of getting feedback for your open source contribution
    - Feel free to ask project maintaners for help!
5. How (not) to update a pull request
    - Not updating latest changes from upstream to feature branch
    - git rebase vs git merge
        - The perils of git rebase on a public repo
6. How to update a pull request v2
    - Update latest changes from upstream to feature branch
    - git fetch && git merge upstream/master
7. Getting your pull request accepted for future releases!
8. Key Takeaways

## Slides

[Women Who Code Singapore Talks.Dev #5 - 28 November 2019 - Contributing to pandas for the first time](https://docs.google.com/presentation/d/1uIuK4MhGZCzBUBuPp7tuVEMT34wsuJcvaQaYLF_wc4I/edit?usp=sharing)

## Video

[Contributing to pandas for the first time - lessons from open source](https://youtu.be/qGPaRTG17ts)

## Quick reflection

It was my first time giving a talk with a more personal slant - an honest sharing of my learning journey in open source. My objective of this talk is to share about the lessons I've learnt in contributing to an open source project for the first time - be it how I do version control with Git, following style guides when writing Python code and docstrings, and contributing to an open source project in general.

I shared this talk idea with Purnima after TalksDev #4, and she was more than happy to give me the opportunity to deliver this talk in TalksDev #5. I initially thought that testing out this talk with a smaller, cosier audience of 10-20 people (mostly women) would be relatively safe - boy, was I wrong. Feedback from the audience range from "Love it, I can relate to that!" to "Hate it, your talk is all over the place!" on the talk barometer scale - given the previous talks at TalksDev, I guess some people in the audience might have preferred a more technical deep-dive rather than a "rabbit-hole" learning journey.

Oh, and since the talk recording is already up on Engineers.SG, would I give the same talk again? Maybe, if I can afford to risk my reputation as a speaker, but definitely not in the near future when I'm still trying to build up my speaking credentials.

## Things that could have been improved

1. Majority of the audience wasn't in the data field - mostly experienced Java/Javascript/Android developers.
2. Visual image of docstring to illustrate how docstring acts as documentation in Python - I can't seem to get docstrings to show up reliably when I'm working with pandas (docstrings don't show up reliably when I'm figuring out MultiIndex.set_levels() for example), so I didn't manage to capture a nice visual image of docstring popups for the talk. *sad face*
3. I decided not to mention too much about the Python Enhancement Proposals (PEP) when talking about the use of style guides (PEP8 and PEP257), as I thought that going into details about PEP would be of more interest to a Python-majority audience (yes, there's even talks about PEPs in PyCon!) and I didn't want to kill off audience interest too early by talking extensively about PEP. Instead, I opted to explain the style guides as general code guidelines similar to those of other programming languages. However, Yue Lin (Director for Women Who Code Singapore) disagreed with my decision not to explain about PEP in more detail in my talk. Maybe I could have still included a little mention about PEP, but nothing more than what it stands for - there's just too much to talk about for PEP in my opinion!
4. Being too personally involved in a talk could risk the perception of "unprofessionalism" - and not in a good way.

## Thing that went well

1. At least half the audience could relate to my talk, my enthusiasm in contributing to open source, and the pains of contributing to open source and using Git
2. I brought my own adaptor and presenter, and arrived at the venue slightly earlier to test out the AV - this is becoming standard operating procedures before the talk itself.
3. I didn't stumble at trying to explain git rebase vs git merge - at least that's better than 1 month ago when I messed up my feature branch!
4. I'm pretty amazed that I still managed to come up with something decent for the slides before my next conference talk - which is on a totally different topic.
