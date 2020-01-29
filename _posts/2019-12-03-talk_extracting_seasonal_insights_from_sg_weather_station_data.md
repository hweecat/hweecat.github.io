---
layout: post
title: "Talk: Making Open Weather Data More Accessible: Extracting Seasonal Insights from Singapore Weather Station Data"
description: "Quick speaker notes on making open weather data more accessible - using Singapore Data.gov.sg APIs as a case study + talk reflection"
excerpt: It started out as a weekend coding exploration of real-time data from the Data.gov.sg APIs, but went on to become something more.
tags: talks
---
---
Where: [Open UP Global Summit](https://www.openup.global/)

When: 1 December 2019

Location: Syntrend Creative Park, Taipei, Taiwan

Resources used:
- [What is Open Data? - by Open Knowledge Foundation](https://opendatahandbook.org/guide/en/what-is-open-data/)
- [What is open data and Why should we care?](https://theodi.org/article/what-is-open-data-and-why-should-we-care/)
- [Realtime Weather Reeadings across Singappore - Data.gov.sg](https://data.gov.sg/dataset/realtime-weather-readings)
- [Scraping Meteorological Data from Data.gov.sg APIs](https://github.com/hweecat/api_scraping_nea_datasets)
- [Tutorial: Time Series Analysis with Pandas](https://www.dataquest.io/blog/tutorial-time-series-analysis-with-pandas/)
- [Time Series Analysis in Python - A Comprehensive Guide with Examples](https://www.machinelearningplus.com/time-series/time-series-analysis-python/)

## Recap

A recap of what I went through during my talk:

1. An intro about myself and why this talk
    - A data engineer from Singapore who loves to travel
    - How many seasons does Singapore have?
2. Extracting Weather Data from Open Government Data Portal
    - Realtime Weather Readings from Data.gov.sg
    - Issues faced in using Data.gov.sg API
        - Nested JSON
        - Inconsistent schema order
    - Open Data - Available, Readable, Accessible
        - Is it enough for open data to be available?
3. Data.gov.sg Weather Data API Scraping
    - What is it + Scope of API Scraping
    - Challenges faced in developing scraping tool
    - Demo
4. Time Series Analysis Demo
    - Extracting Seasonal Insights from Scraped Weather Data
5. Key Takeaways

## Slides

[openupsummit - 1 December 2019 - Making Open Weather Data More Accessible: Extracting Seasonal Trends from Singapore Weather Station Data](https://docs.google.com/presentation/d/1IIumhbnO-FzEjlrHIQHj-qbIKNywJG0lNmYqxtX1PL0/edit?usp=sharing)

## GitHub Repository for Demo

[hweecat/talk_extracting-singapore-seasons-data](https://github.com/hweecat/talk_extracting-singapore-seasons-data)

## Video

[Open UP Summit 2019 Ong Chin Hwee - Extracting Seasonal Insights from Singapore Weather Station Data](https://www.youtube.com/watch?v=x8CtEtn0vsc)

## Quick reflection

This was my first international conference, and my first time delivering a talk with a demo segment.

Why did I choose to conduct a demo? While I was preparing my talk, I was thinking of what would be the best way to bring out the core idea of making open realtime weather data more accessible to anyone - developers and non-developers included. While preparing time series visualizations from the weather readings extracted from the Data.gov.sg APIs, I thought: "Why not showcase both the usage of the scraping tool + seasonal insights from time series visualizations to keep the suspense? That'd also demonstrate how the data is made more accessible to the audience."

I tested out both demo segments until 3am to ensure that I could showcase the demo with the latest weather readings. On the day of the talk itself, Murphy's Law of Demos struck with a Wifi connection that kept dropping every 10 minutes and issues with my Jupyter server. I made a snap decision to truncate my demo, explain a bit about the scraping code and showcase an offline notebook of the time series visualization with all the codes executed beforehand. Not too sure if the audience picked up that I was kinda "panicking" with my demo, though at least two of the speakers couldn't tell that it was only my first year of speaking or conducting a demo on stage (I'll take that as a compliment!).

Would I give a talk with a demo next time? Why not, but I'd prepare way beforehand for all sorts of technical scenarios next time.

## Things that could have been improved

1. Relative smaller audience - probably because there was an ongoing workshop and a demo on Generative Adversarial Networks (GAN) at the same time.
2. Audience was a mix of data and design people. I did try to explain the technical concepts and Python libraries during my talk so that the non-technical folks could also follow along, but I suspect at least half of the audience might have still been lost.
3. Even some speakers didn't know that I'm a speaker. :( Maybe I should have a more obvious speaker vibe?

## Thing that went well

1. My API scraping demo, which kept failing before my talk, worked smoothly (though slowly) on stage when I instructed it to scrap 6 days of data.
2. At least two people approached me to say that they liked my talk + demo, so that's better than zero!
