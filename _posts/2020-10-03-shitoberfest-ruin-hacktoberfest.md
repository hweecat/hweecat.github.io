---
layout: post
title: "#Shitoberfest: How free T-shirts ruined #Hacktoberfest2020"
description: "A cautionary tale on how incentivising pull requests with free T-shirts indirectly led to a ruined experience for open-source contributors"
excerpt: "Hacktoberfest"
tags: reflection
---
---

## About Hacktoberfest

Hacktoberfest is an annual event organized by [DigitalOcean](https://digitalocean.com) that celebrates open-source contributions. Occuring every October, the goal of Hacktoberfest is to encourage developers (of all backgrounds and skill level) and companies to make positive contributions to the open-source community.

To encourage developers to make more open-source contributions, the first 70,000 participants who successfully makes 4 pull requests (PRs) between 1 - 31 October in any time zone to *any* public repository on GitHub are eligible to receive a prize in the form of a limited-edition T-shirt. Yes, no limits.

Alternatively, participants can choose to plant a tree instead of getting a free T-shirt in year 2020 - as a show of support for #sustainability.

All these sound like an initiative with good intentions on paper - incentivise developers to contribute to open-source projects. Unfortunately, the organizers underestimated the extent of what people are willing to do for the sake of getting free T-shirts (or freebies in general).

## How low-quality PRs turned #Hacktoberfest2020 into #Shitoberfest

On October 1st after work, I was just minding my business scrolling Twitter and searching GitHub for interesting #hacktoberfest issues to work on - and then I saw this tweet from a hilariously-named Twitter account called [@shitoberfest](https://twitter.com/shitoberfest) that seems to be dedicated towards curating spam PRs.

{::options parse_block_html="false" /}

<div class="center">

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">Hi, I&#39;m <a href="https://twitter.com/shitoberfest?ref_src=twsrc%5Etfw">@shitoberfest</a>. Do you maintain an opensource project? <br><br>Send a screenshot of bullshit drive by pull-requests caused by <a href="https://twitter.com/hashtag/hacktoberfest?src=hash&amp;ref_src=twsrc%5Etfw">#hacktoberfest</a> and tag <a href="https://twitter.com/shitoberfest?ref_src=twsrc%5Etfw">@shitoberfest</a> for curation and amplification. <a href="https://t.co/50wuPISbYb">pic.twitter.com/50wuPISbYb</a></p>&mdash; #shitoberfest (@shitoberfest) <a href="https://twitter.com/shitoberfest/status/1311646233128181760?ref_src=twsrc%5Etfw">October 1, 2020</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script> 

</div>

"What on earth is happening?" I wondered while looking through the tweets in the account and realizing that the PRs seemed to follow similar patterns - with "Awesome Project" and other nonsensical edits to READMEs.

Next, I saw this tweet by [Gael Varoquaux (@GaelVaroquaux)](https://twitter.com/GaelVaroquaux) who is a co-founder of the [scikit-learn project](https://scikit-learn.org). And it looks like the spam PR situation is MASSIVE.

{::options parse_block_html="false" /}

<div class="center">

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">A difficulty in a popular open-source project: people submit contributions to gain credit, but not always useful (below: no content + invalid markup).<br><br>scikit-learn had 10000 pull requests, 732 still open.<br>Reviewing them is costly qualified labor.<br><br>Rapid closing harms openness 🤷 <a href="https://t.co/6DKcB2aHmO">pic.twitter.com/6DKcB2aHmO</a></p>&mdash; Gael Varoquaux (@GaelVaroquaux) <a href="https://twitter.com/GaelVaroquaux/status/1311582305559998465?ref_src=twsrc%5Etfw">October 1, 2020</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script> 

</div>

I highly recommend checking out [@shitoberfest](https://twitter.com/shitoberfest) for a good laugh at some of the spam PRs. It's so bad that it's hilarious to the casual observers who don't care too much about free T-shirts.

It's not so funny for [open-source maintainers](https://blog.domenic.me/hacktoberfest/) though - they had to do extra work cleaning up spam PRs and tagging them as "invalid" or "spam" so that those spam PRs do not count towards the Hacktoberfest tally.

## Cause

What caused #Shitoberfest? It wasn't that massive a problem last year even though the problem of "spam PRs" have always been there, so it could not have been caused solely by the incentive of getting a free T-shirt.

[This excellent narrative post by Joel Thoms](https://joel.net/how-one-guy-ruined-hacktoberfest2020-drama) explains in detail what caused the #Shitoberfest drama (thanks [Eugene Yan](https://twitter.com/eugeneyan) for sharing that gem!): a YouTuber called CodeWithHenry who demonstrated how easy it is to make a Pull Request to a repo in order to win free stuff - by creating a low-quality PR.

This led to his viewers following **exactly** what he did, leading to this **#Shitoberfest**.

Without alluding to any particular nationality/race/ethnicity, he was speaking a non-English language in that demonstration video. That video has since been removed.

## Psychology and Aftermath

The next question is: What is the psychology behind those people who created spam PRs just for the sake of getting a free T-shirt?

There are two key factors that might have influenced such behaviour:

1. [The Psychology of Free](https://thedecisionlab.com/insights/consumer-insights/impact-free-consumer-decision-making/) - in this case, the psychology of trying to get free stuff with as low an effort or opportunity cost as possible.
2. [The Psychology of FOMO (Fear of Missing Out)](https://online.king.edu/news/psychology-of-fomo/) - in this case, the fear of missing out on a "limited edition" T-shirt that spells "bragging rights" after watching a YouTuber getting one from making PRs.

It's human nature to love free stuff, especially if there's a way to get them without spending too much effort and time - it's like getting an undeserved gift. It's also human nature to be subject to peer pressure and FOMO when seeing others getting stuff that we wish we had but do not have.

However, **it's not fair to exploit human nature in a way that causes masses of people to generate spam that leads to wastage of other people's limited resources**.

It is also **not fair to other developers who genuinely want to learn through contributing to open-source projects that they care about, be it their own projects or projects by other developers**.

The problem is that:

1. DigitalOcean created the limited T-shirt incentive to attract more people to contribute to any public GitHub repositories as part of Hacktoberfest.
2. CodeWithHarry wanted to share with his audience about ways to get free stuff through making PRs for Hacktoberfest, and demonstrated with a low-quality PR for convenience and speed - without explicitly mentioning in the video that the audience should not follow exactly what he did as it is a low-quality PR *just for demonstration*.
3. Some of those spammers might probably be new to open source and/or Hacktoberfest, do not know how to contribute meaningfully, but really want that free Hacktoberfest T-shirt anyway.

And these cumulated in a ruined Hacktoberfest and change of rules.