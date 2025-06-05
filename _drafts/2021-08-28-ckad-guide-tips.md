---
layout: post
title: "8 Tips for Passing CKAD - A(n) (In)formal Guide for Data Professionals"
description: "How I cleared CKAD in my first attempt, reasons to consider getting certified in k8s as a data professional, and tips for passing CKAD"
excerpt: "At the start of August 2021, I passed the Certified Kubernetes Application Developer (CKAD) exam on my first attempt. It was my first-ever IT certification since I stumbled into the data industry, and I would not have taken the leap if not for the Linux Foundation Training (LiFT) scholarship which provided me with the opportunity to pursue the certification risk-free. The journey to getting certified for Kubernetes (or k8s for short) was not easy - what it takes is patience, grit and loads of deliberate practice."
tags: til
author: ongchinhwee
largeimage: /images/ckad_from_cncfsite.png
---
---

## My experience in getting certified on K8s

At the start of August 2021, I passed the Certified Kubernetes Application Developer (CKAD) exam on my first attempt.

It was my first-ever IT certification since I stumbled into the data industry, and I would not have taken the leap if not for the Linux Foundation Training (LiFT) scholarship which provided me with the opportunity to pursue the certification risk-free.

{::options parse_block_html="false" /}

<div class="center">

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">I have passed the Certified Kubernetes Application Developer (CKAD) exam on my first try with 88%! 🥳<br><br>Thank you so much to <a href="https://twitter.com/linuxfoundation?ref_src=twsrc%5Etfw">@linuxfoundation</a> <a href="https://twitter.com/CloudNativeFdn?ref_src=twsrc%5Etfw">@CloudNativeFdn</a> for the scholarship and exam simulator, and <a href="https://twitter.com/kodekloud1?ref_src=twsrc%5Etfw">@kodekloud1</a> for the hands-on labs.<a href="https://t.co/Pe6rAPDBrP">https://t.co/Pe6rAPDBrP</a><a href="https://twitter.com/hashtag/k8s?src=hash&amp;ref_src=twsrc%5Etfw">#k8s</a> <a href="https://twitter.com/hashtag/Kubernetes?src=hash&amp;ref_src=twsrc%5Etfw">#Kubernetes</a></p>&mdash; Ong Chin Hwee 🐼 (@ongchinhwee) <a href="https://twitter.com/ongchinhwee/status/1422069660866924544?ref_src=twsrc%5Etfw">August 2, 2021</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

</div>

The journey to getting certified for Kubernetes (or k8s for short) was not easy, considering that my exposure to k8s prior to preparing seriously for the exam was limited to:

1. An introduction workshop to K8s organized by JuniorDevSG before the pandemic
2. Ad-hoc exploration on Qwiklabs (courtesy of Google Cloud's #MajulahGCP quests)

My point is: **it is possible to pass CKAD without vast experience in DevOps and k8s**.

What it takes is patience, grit and *loads of deliberate practice*.

## What is Certified Kubernetes Application Developer (CKAD)?

The Certified Kubernetes Application Developer (CKAD) certification is geared towards developers who will be building, monitoring and troubleshooting scalable applications and tools running on Kubernetes.

The requirement to earn the CKAD certification is to "score a passing grade of 66% on a 2-hour online proctored performance-based exam, which consists of a set of performance-based items (problems) to be solved in a command line, running Kubernetes".

In short, the CKAD exam is a practical hands-on exam consisting of around 19 questions that is fully on the command-line.

No multiple-choice questions (MCQs), no *tikam-tikam*.

You really need to know what you are doing in order to pass the exam. It is important to understand what you are doing and build up the necessary fundamentals when learning k8s.

## Why another guide for CKAD?

There's loads of guides and blog posts for CKAD preparation and tips on the Internet. Why am I writing  another guide for CKAD?

If you are a **data professional who did not start out with software engineering experience**, it is likely that you would be concerned about your readiness in getting certified for k8s.

Trust me, I've had serious doubts about whether I can pass the CKAD as an mid-level (working towards senior-level) data professional without software engineering experience.

While I know enough about Docker to understand some of its key concepts and create my own Docker containers, my typical comfort level in Linux and vim are limited to the bare basic commands needed to navigate the command-line (`ls`, `rm`, `cd`, `wget`, `pwd`, insert/exit commands in vim). Enough to get around as a data professional, but definitely not a pro.

You do not need to be an expert in Docker or command-line or YAML to learn k8s and/or get certified in CKAD. The CKAD exam is testing for your understanding of developing applications on Kubernetes, not your expertise in the command-line (though being good at command-line helps).

As long as you have worked with command-line before and know how to use Docker, **you are ready to get started**.

Set a goal, work towards it one step at a time, and don't pressure yourself into learning everything about Kubernetes within 3 - 4 weeks.

That being said, you might need to give yourself a bit more time for groundwork before preparing for CKAD.

## Tip 1: Groundwork is essential

Thinking of jumping straight into Kubernetes? Not so fast.

Just like how it isn't generally a good idea to jump straight into machine learning without knowing the fundamentals of linear algebra and statistics (and how machine learning extends upon these concepts), it's not a good idea to jump straight into Kubernetes without understanding the concept of containers and the use case for container orchestration.

In short, you need to understand:

1. why the newer technology or approach exists
2. what prior fundamental concepts it is built upon
3. what problems or limitations the newertechnology or approach aims to solve

Kubernetes is a container orchestration tool built by Google to manage containerized applications at scale. To understand Kubernetes, first you need to build up a solid understanding of what containers are and what problems containers solve in deploying applications.

[Docker for Beginners by Prakhar Srivastav](https://docker-curriculum.com/) is the tutorial I used to get started with learning Docker and containers in general. Another good resource that I would recommend is [Introduction to Docker containers](https://docs.microsoft.com/en-us/learn/modules/intro-to-docker-containers/) on Microsoft Learn.

After understanding containers, you can then proceed with an introductory course on Kubernetes to get a feel of what Kubernetes is.

I attended the first run of Daniele Polencic's workshop "Zero to Kubernetes" on JuniorDevSG Developer's Gym in 2019. A recording of a repeat run of the workshop can be found on this [link](https://www.youtube.com/watch?v=Bbh7K1d0eZY).

To reinforce these concepts, I also made use of [Qwiklabs](https://qwiklabs.com) to get a hands-on feel of deploying containerized applications in the cloud using Docker and Kubernetes - courtesy of Google Cloud Singapore's #MajulahGCP campaigns. Thanks Google Cloud!

Setting the groundwork helped significantly when I finally started seriously preparing for CKAD one month before the expiration date, as I could grasp the concepts in the CKAD curriculum more quickly by linking them with previously-learned concepts and patterns.

## Tip 2: Buy a CKAD prep course with hands-on labs (when it is on sale!)

A common tip for CKAD prep is to take Mumshad Mannambeth's course [Kubernetes Certified Application Developer (CKAD) with Tests](https://www.udemy.com/share/101Eno3@619J4tlmXIZZaoC59w1PIFytEFEaPCGtYtuQQSvrnp_eF9EczfSRsiTHZkeIbrOx/) on Udemy, and for good reason.

The course comes with hands-on labs, which are very useful and helps save a lot in setup time when practicing for a hands-on exam such as CKAD.

Money-saving tip: Look out for Udemy flash sales where the course price could potentially drop as low as S$15!

## Tip 3: 