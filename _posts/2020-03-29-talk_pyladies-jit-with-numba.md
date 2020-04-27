---
layout: post
title: "Lightning Talk: Just-in-Time with Numba - 7-minute PyLadies version"
description: "Quick speaker notes + reflection on my first lightning talk with PyLadies"
excerpt: One fine day in the morning of 28 March 2020 Singapore time, I came across a tweet from PyLadies calling for lightning talk submissions for their International Women's Month Lightning Talks Zoom call. Just a day ago, my data scientist friend mentioned about Numba on Facebook, and I happened to have spoken quite a bit about Numba in my first conference talk last year.
tags: talks
---
---
Where: [PyLadies International Women's Month Lightning Talks](https://pyladies.com/)

When: 28 March 2020

Location: Virtual

Resources used:
- [5-minute Guide to Numba](http://numba.pydata.org/numba-doc/latest/user/5minguide.html)

## Recap

A recap of what I went through during my talk:

1. Bottlenecks in a data science project
    - Data Preprocessing + Python as interpreted language
2. Compiled vs Interpreted Languages
    - Running machine code (executable) vs running bytecode in virtual machine
3. What is Just-in-Time?
    - Source code to native machine code at runtime
4. Just-in-Time with Numba
    - Two modes of execution: @jit and @njit (no-Python mode)
5. Practical Implementations
6. Key Takeaways

## Slides

[PyLadies - 28 Mar 2020 - Just-in-Time with Numba](https://docs.google.com/presentation/d/1PaKq_XTV9YE1WgcGLuq6XsyEEk9BHQ4RhaduYiEwZ6g/edit?usp=sharing)

## GitHub Repository for Demo

[hweecat/talk_jit-numba](https://github.com/hweecat/talk_jit-numba)

## Video

Pending recording from PyLadies

## Quick reflection

One fine day in the morning of 28 March 2020 Singapore time, I came across a tweet from PyLadies calling for lightning talk submissions for their International Women's Month Lightning Talks Zoom call. Just a day ago, my data scientist friend mentioned about Numba on Facebook, and I happened to have spoken quite a bit about Numba in my first conference talk last year. Since it was technically still the night of 27 March 2020 across the globe (they did say to submit by 27 March 2020 anywhere in the world), I got down to work and put together two short demos and a couple of slides on Numba for my lightning talks submission.

Why a lightning talk after delivering a bunch of full-length talks?

1. There's no active PyLadies chapter in Singapore and I have never attended a PyLadies session before. Why not attend my first-ever PyLadies event with a bang?
2. I'm a little peeved that I don't get to fly to Europe in April for my first European conference talk - no thanks to COVID-19.
3. Honestly I'm still feeling pretty darn insecure about my speaking and I don't think I'm succinct enough or "up to the mark" as a speaker compared with the more experienced and famous folks (and I actually feel that sense of insecurity intensely as a perfectionist). Giving a lightning talk with a 5-7 minutes time limit might just force me to condense my talk material, get to the point, and throw aside my fear of boring the audience with a full-length talk padded with fluff.
4. Back to my feelings of insecurity about my speaking - I just wanted to try something out of my comfort zone and feel as if I'm doing things for the first time again.
5. Learning by speaking - even if it's something small that you've started learning!

Back to my lightning talk - I kinda rambled a bit at the start when introducing myself ('cos I'm kinda "exotic fresh Southeast Asian face" among all the wonderful women Pythonistas in the Zoom teleconference), but the rest of the talk went pretty smoothly without much of a hitch. The ladies enjoyed the talk, I enjoyed the lightning talks from fellow women Pythonistas from various continents (and learnt new functions, libraries and discovered really cool community stuff around the world), and we had a nice breakout session where I had a really enjoyable chat with Abigail Dogbe about the work that she does as organizer of PyLadies Ghana. In fact, I'm actually getting really excited about the next virtual PyLadies Zoom session with more lightning talks and breakout sessions!

As a side note, it's a coincidence that I came across the advice to "just show up" recently. Guess I need to keep showing up for potential opportunities out there and trust in the process.