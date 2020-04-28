---
layout: post
title: "Lightning Talk: Just-in-Time with Numba - 10-minute Remote Python Pizza 1.0 version"
description: "Quick speaker notes + reflection on my first international lightning talk at a remote conference"
excerpt: I have spoken quite a bit about Numba in my first conference talk last year, and felt it deserved more attention. Hence, I decided to craft a jam-packed lightning talk that focuses on the non-trivial aspects of Numba - all in 10 minutes!
tags: talks
---
---
Where: [Remote Python Pizza 1.0](https://remote.python.pizza/)

When: 25 April 2020

Location: Remote (@ your couch!)

Resources used:
- [Compiled vs Interpreted Languages - freeCodeCamp Guide](https://guide.freecodecamp.org/computer-science/compiled-versus-interpreted-languages/)
- [Just in Time Compilation - freeCodeCamp Guide](https://guide.freecodecamp.org/computer-science/just-in-time-compilation/)
- [What’s the difference between a compiled and interpreted language?](https://www.programmerinterview.com/general-miscellaneous/whats-the-difference-between-a-compiled-and-an-interpreted-language/)
- [Compiler and Interpreter: Compiled Language vs Interpreted Programming Languages](https://www.youtube.com/watch?v=I1f45REi3k4)
- [5-minute Guide to Numba](http://numba.pydata.org/numba-doc/latest/user/5minguide.html)
- [Numba architecture](https://numba.pydata.org/numba-doc/latest/developer/architecture.html)

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
    - Numba compiler architecture
        - Concept of Intermediate Representation (IR)
        - Type inference frontend + LLVM backend
5. Practical Implementations
    - @jit mode with Numba-incompatible types (e.g. Pillow)
    - @njit mode with Numba-compatible types (e.g. numpy)
6. Key Takeaways

## Slides

[Remote Python Pizza - 25 April 2020 - Just-in-Time with Numba](https://docs.google.com/presentation/d/1hX-k6wg7NL3KTS-p4XfFGhea0zUH6pA-nWuR1m8C-s4/edit?usp=sharing)

## GitHub Repository for Demo

[hweecat/talk_jit-numba](https://github.com/hweecat/talk_jit-numba)

## Video

Pending publicly-available recording from Remote Python Pizza

## Quick reflection

The first time I gave a talk involving Numba was during my first conference talk last year, but the first time I gave a talk focusing on Numba was at PyLadies International Women's Month Lightning Talks. Encouraged by the warm reception from the PyLadies folks, I submitted a proposal for a 10-minute lightning talk on Numba for Remote Python Pizza without really expecting much - if it got accepted I'm contributing to a good cause through sharing my knowledge with a lightning talk, and if it didn't get accepted I could still choose to contribute to a good cause by chipping in for a ticket since the conference proceeds go towards Doctors Without Borders. Turns out, my talk proposal got accepted, so I spent some time rehearsing and doing a bit more research on Numba in preparation for my first-ever lightning talk at a conference in a remote setting.

It feels different giving a talk at a remote conference, not knowing how the unknown number of people in the audience feels or thinks about your talk - what more giving a lightning talk at a remote conference for the first time? Initially, I even felt a bit intimidated looking at the impressive lineup of speakers and thinking "oh my goodness I'm like the representative Southeast Asian / Singaporean speaker so I better not embarrass my country" (even though I'm not the only Asian among the speaker lineup) - I was experiencing some form of heightened anxiety during the first week of "Circuit Breaker" and felt the "imposter syndrome" even more strongly.

To ground myself mentally while preparing for my lightning talk, I did the following steps:

1. Fear of messing up? Remind myself why I chose to give a remote lightning talk - to try something out of my comfort zone, to get used to giving talks remotely, and to improve and learn how to communicate more succinctly as a speaker from the experience.
2. Feeling like an impostor compared with the more experienced folks? Remind myself that I am given the opportunity to speak alongside a great lineup of speakers, and I belong there as much as how they belong there.
3. Feeling like I don't matter as much? Remind myself that every bit of effort counts - I'm chipping in towards raising funds for Doctors Without Borders by speaking, and someone might find my talk useful.
4. Still feeling anxious? Acknowledge the feeling, take deep breaths, and listen to motivational podcasts and calming instrumentals.

The speaker-onboarding session before the conference was really helpful though - I tested the Zoom setup, ran through some of the slides, and received crucial feedback that led me to add additional slides on the Numba compiler architecture in order to explain the two modes of execution in Numba.

Back to my lightning talk - I kinda stumbled a bit at the start and towards the end as there were too many similar-sounding words in my talk, but the rest of the talk went pretty smoothly and I managed to deliver everything I planned to speak about within 10 minutes. My setup was a bit clumsy since my "second screen" was my work laptop with my speaker notes, and I ended up looking towards my speaker notes at a slightly awkward angle when discussing about the more technical details. I didn't dare to look at the conference Discord channel throughout my talk for fear of negative feedback, so I ended up being reminded that my time is almost up on Zoom - luckily I was already towards the end of my talk by then. At the end of my talk, I noticed that I was sweating profusely and my back was drenched, even though I was in a room with air-conditioning.

My initial post-talk thought was "okay I finally did the thing even though I stumbled on my words". I was pleasantly surprised to see the overwhelmingly warm response and feedback on the conference Discord channels AND on Twitter - turns out, there are people who loved my talk! 

As a side note, it's a coincidence that I came across the advice to "just show up" recently. Guess I need to keep showing up for potential opportunities out there and trust in the process.

### Things that could have been improved

1. I stumbled a bit while explaining how the two modes of execution (@jit and @njit) works within the Numba compiler architecture - especially when there's Numba IR and LLVM IR involved.
2. When rewatching the livestream, it seemed pretty obvious to me that I was looking at a second laptop with the speaker notes since my face wasn't looking straight onto the webcam.
3. My wireless headset microphone was a bit loud and my voice got distorted on the livestream - or maybe my speaking voice was too loud for my microphone.
4. I'm still using too many "so......" and "right......" in my talks until I suspect it exposes my "Singlish-ness" on an international stage. Hand gesticulations and "hand-flailing" don't work as well for a remote talk either.

### Things that went well

1. My talk went well without major hiccups and I delivered everything I planned to share within 10 minutes - everything from compiled vs interpreted languages, JIT compilation, Numba, LLVM etc.
2. I received a lot more new followers and plenty of praise on Twitter - and more praise on the conference Discord channel!
3. I'm really glad that there were people in the remote audience who noticed the non-trivial efforts I put in to explain complex concepts in a way that makes it easier for people to understand. Compiler architecture
4. There were Singaporeans among the remote audience - it really means a lot to me as a Singaporean female (and doubly underrepresented) tech speaker when they tell me I did an awesome job and I did Singapore proud! :')