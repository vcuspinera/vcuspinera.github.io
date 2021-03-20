---
title: "Canada response to Covid-19"
author: "Leo Cuspinera, Victor Cuspinera"
collection: projects
type: "Personal_projects"
permalink: /projects/2020/canada-covid
venue: "GitHub.com"
date: 2021-03-22
location: "Mexico City, Mexico"
tags:
  - Canada
  - Covid-19
  - Sentiment Analysis
  - NLP
  - Python
---

Sentiment analysis of people's __tweets__ to measure the impact of the __Canadian Government policies__ to help Canadians cope with the __Covid-19__.  
$\bigstar$ *[Click here](https://github.com/vcuspinera/Canada_response_covid) to look at the original GitHub repository of this project.*  

*Authors: Leo Cuspinera ([cuspime](https://github.com/cuspime)), Victor Cuspinera ([vcuspinera](https://github.com/vcuspinera))*  

<center><img src="/images/canada-covid_logo.png" width="180" /></center>

## Overview
The idea of this project was born on March 11th of 2020, when the Prime Minister of Canada, Justin Trudeau, announced a series of [policies to help Canadians cope with the Covid-19](https://youtu.be/YunI2PNZKxg).

The objective is to analyse the Canadian Government response to Covid-19 through the perception of the people by making sentiment analysis on people's tweets. For this analysis we download tweets published between February 1st and April 30th of 2020, that mention any of the following Canadian Government Twitter accounts: [@Canada](https://twitter.com/canada?lang=en), [@CanadianPM](https://twitter.com/CanadianPM), [@JustinTrudeau](https://twitter.com/JustinTrudeau?s=20) and [@GovCanHealth](https://twitter.com/govcanhealth?lang=en). For this task we use the [`snscrape` library](https://github.com/vcuspinera/Canada_response_covid/blob/master/src/twitter-search_v3_snscrape.ipynb). After getting the database we clean it by preprocessing the tweets to delete some of the sensible information as emails and urls. 

## Explanatory Data Analysis (EDA)
When comparing the tweets per day by Canadian Government Twitter accounts, we find that between February and April 2020, the [@JustinTrudeau](https://twitter.com/JustinTrudeau) account had between 3.0 and 21.4 thousand tweets per day, [@Canada](https://twitter.com/Canada) had between 98 and 470 tweets, [@CanadianPM](https://twitter.com/CanadianPM) had between 104 and 1,179 tweets, and [@GovCanHealth](https://twitter.com/GovCanHealth) between 30 and 1,182 tweets per day.

<img src="/images/canada-covid_EDA_tweets.png" width="650">

We also use a heatmap to identify the days where most people published tweets, in the period from February 1st to April 30th. For this, we calculate the Moving Averages with 7-day window, and normalize these averages by account using minimum and maximum number of tweets. With this analysis we identify the days with more tweets, removing weekly seasonality. Here we can identify an increase in number of tweets for all the Canadian Government's Twitter accounts from March 11th onwards, with a peak of tweets between March 14th and 17th.

<img src="/images/canada-covid_EDA_heatmap.png" width="800">

⭐️ More details of the EDA are available in this [link](https://github.com/vcuspinera/Canada_response_covid/blob/master/src/eda.ipynb).

## Sentiment Analysis
Most tweets were written in English (85.5%), so for the sentiment analysis we select only tweets written in English and use descriptive statistics based in counts of words, word clouds, time series and scores get by [spaCy](https://spacy.io).

When comparing word clouds of tweets published before and after the announcement on March 11th, 2020, we found that most used words and their repetitions are very similar among both groups.

Additionally, we explore sentiment analysis with spaCy's `polarity` and `subjectivity`, by looking at the log number of tweets.

In this case, tweets published before and after the announcement have very similar Polarity and Subjectivity curves. While the polarity in both groups is very similar, in both cases it is skewed to have positive tweets. In the other hand, these tweets were much more objective than subjective.

<img src="/images/canada-covid_sentiment_PolarSubject.png" width="750">

We also perform hypothesis testing polarity and subjectivity on tweets before and after the announcement on sub-samples of tweets, but we couldn't reject that both means of these measures were different.

We also use Time Series to find the Trend of polarity and number of tweets. In short, while the trend in sentiment decrease for the [@Canada](https://twitter.com/canada?lang=en) account, tweets related with the Canadian Prime Minister ([@CanadianPM](https://twitter.com/CanadianPM) and [@JustinTrudeau](https://twitter.com/JustinTrudeau?s=20)) had a positive impact after the announcement. In addition, the [@GovCanHealth](https://twitter.com/govcanhealth?lang=en) had almost the same trend in polarity levels.

<img src="/images/canada-covid_sentiment_trend.png" width="750">

Finally, the announcement also impacted in the volume of tweets, as well the actions and reactions of users increasing the number of likes, replies, retweets and quotes.

<img src="/images/canada-covid_sentiment_reactions.png" width="700">

[⭐️ click here](https://github.com/vcuspinera/Canada_response_covid/blob/master/src/sentiment_analysis.ipynb) to see more details about the sentiment analysis.

## Final comments
On the analysis we find that the announcement on March 11<sup>th</sup>, and the following announcements of the Government policies related with COVID-19, had an impact in the volume and sentiment of tweets: 

- __Sentiment__: while the overall sentiment of tweets is positive, the announcement had different effect for the Government accounts. While the effect on [@Canada](https://twitter.com/canada?lang=en) account was a decrease in the average polarity, in the other hand we identify a rise in the positive sentiment of tweets related with the Canadian Prime Minister (which means an increase in the polarity levels of [@CanadianPM](https://twitter.com/CanadianPM) and [@JustinTrudeau](https://twitter.com/JustinTrudeau?s=20) accounts). The [@GovCanHealth](https://twitter.com/govcanhealth?lang=en) account was stable in polarity level before and after the announcement. 
- __Volume__: we observed an increase in the total number of tweets and the average tweets per day. Also, the noncement affected the volume of actions and reactions of users increasing the number of likes, replies, retweets and quotes.
