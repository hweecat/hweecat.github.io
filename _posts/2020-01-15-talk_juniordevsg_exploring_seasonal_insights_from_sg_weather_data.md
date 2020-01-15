---
layout: post
title: "Talk: Making Open Weather Data More Accessible: Extracting Seasonal Insights from Singapore Weather Station Data"
description: "Quick speaker notes on making open weather data more accessible - using Singapore Data.gov.sg APIs as a case study + talk reflection"
excerpt: It started out as a weekend coding exploration of real-time data from the Data.gov.sg APIs, but went on to become something more.
---
---
Where: [JuniorDevSG Code and Tell January 2020 Meetup](https://www.meetup.com/Junior-Developers-Singapore/events/267507133/)

When: 14 January 2020

Location: 90 Seconds HQ

Resources used:
- [Realtime Weather Reeadings across Singappore - Data.gov.sg](https://data.gov.sg/dataset/realtime-weather-readings)
- [Scraping Meteorological Data from Data.gov.sg APIs](https://github.com/hweecat/api_scraping_nea_datasets)
- [Tutorial: Time Series Analysis with Pandas](https://www.dataquest.io/blog/tutorial-time-series-analysis-with-pandas/)
- [Time Series Analysis in Python - A Comprehensive Guide with Examples](https://www.machinelearningplus.com/time-series/time-series-analysis-python/)

## Recap

A recap of what I went through during my talk:

1. An intro about myself and why this talk
    - A data engineer from Singapore
    - How many seasons does Singapore have?
2. Extracting Weather Data from Open Government Data Portal
    - Realtime Weather Readings from Data.gov.sg
    - Issues faced in using Data.gov.sg API
        - Nested JSON
3. Data.gov.sg Weather Data API Scraping
    - What is it + Scope of API Scraping
    - Design considerations
        - Slow connection
        - API working but no data for specific date
        - Nested JSON to pandas DataFrame conversion
    - Demo
        - Additional user design considations
4. Time Series Analysis Demo
    - Extracting Seasonal Insights from Scraped Weather Data
5. Key Takeaways

## Slides

[JuniorDevSG Code and Tell - 14 January 2020 - Exploring Seasonal Insights from Singapore Weather Station Data](https://docs.google.com/presentation/d/15azdPH_ZuvdoIMI0gyTIFOcv-DqsO_H2Z_x_k1bhie8/edit?usp=sharing)

## GitHub Repository for Demo

[hweecat/talk_extracting-singapore-seasons-data](https://github.com/hweecat/talk_extracting-singapore-seasons-data)

## Video

[Exploring Seasonal Insights from Singapore Weather Station Data - Junior Developers Singapore](https://youtu.be/gNF8D8AkCgY)

## Quick reflection

This talk was first delivered at Open UP Global Summit 2019, and features a demo segment for the second half of the talk. More details on my design considerations for the talk + demo [here](https://hweecat.github.io/talk_extracting_seasonal_insights_from_sg_weather_station_data/)

I tested out both demo segments to ensure that I could showcase the demo with the weather readings for December 2019. On the day of the talk itself, I decided to rely on my 2GB-data-per-day SIM card to minimise reliance on the WiFi at the venue and ran the Jupyter notebooks beforehand for showcasing of the data scraping and data visualization codes. As it was "Code and Tell" and I did want to code and tell, I showcased the command-line interface of my weather station data scraping tool live and proceeded straight to sharing about my code design considerations while waiting for the scraping tool to finish running. Why waste time waiting, right?

The presentation screen was a little small and I had to squint to look at my slides (I'm just too used to presenting with a large screen on stage I guess?); fortunately, it wasn't my first time delivering the talk and hence I didn't end up panicking during the demo this time.

## Things that could have been improved

1. The data folks were all at DataScience SG. ::sadface::
2. I still overshot very slightly for my demo even though I went pretty fast already.
3. No one (except one person + my friend) approached me after the talks were over, so I ended up trying to look out for people to approach (and not being successful in doing that) instead. What's with people approaching speakers after their talks?

## Thing that went well

1. Pretty sizeable audience this time - around 50 - and slightly more responsive to my jokes!
2. I managed to switch pretty smoothly between my API scraping demo and my Jupyter notebook to illustrate my code, which means practice makes perfect.
3. One of NodeFlair's co-founders approached me to say that he liked that my talk + demo was very relatable as it was about a topic that everyone could identify with - the weather. Also got a few more Twitter followers and mentions. Not too bad I guess?
