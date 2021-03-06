---
title: "Canada response to COVID-19"
author: "Leo Cuspinera, Victor Cuspinera"
collection: projects
type: "Personal_projects"
permalink: /projects/2021/canada-covid
venue: "GitHub.com"
date: 2021-03-23
location: "Venice, Italy / Mexico City, Mexico"
tags:
  - Canada
  - COVID-19
  - Sentiment Analysis
  - NLP
  - Python
---

The idea of this project was born on March 11th of 2020, when the Prime Minister of Canada, Justin Trudeau, announced a series of [policies to help Canadians cope with the COVID-19](https://youtu.be/YunI2PNZKxg). The objective is to __measure the impact of the Government policies__ to help Canadians cope with the __COVID-19__, studying people's perception by making __sentiment analysis__ on users' tweets, before and after the Prime Minister's announcement.  
$\bigstar$ *[Click here](https://github.com/vcuspinera/Canada_response_covid) to look at the original GitHub repository of this project.*  

*Authors: Leo Cuspinera ([cuspime](https://github.com/cuspime)), Victor Cuspinera ([vcuspinera](https://github.com/vcuspinera))*  

<br>
<center><img src="/images/canada-covid_logo.png" width="180" /></center>
<br>
<div style="text-align: right">
  <font size="3">
    <i>“Our message to Canadians is clear: to every worker and business, in every and<br> 
        territory, we have your back and we will get through this together.”</i><br>
    <span style="color:gray">— Justin Trudeau, Prime Minister of Canada. Press conference on March 11th, 2020.</span>
  </font>
</div>

## Downloading tweets
To compare the public opinion before and after Trudeau's announcement in the Twittersphere, the first obvious step is getting the tweets. We decided to make a thorough scrapping of tweets using [`snscrape` library](https://github.com/vcuspinera/Canada_response_covid/blob/master/src/twitter-search_v3_snscrape.ipynb), from February 1st 2020 to April 30th 2020 that mentioned at least one of the four aforementioned accounts of the Canadian Government: [@Canada](https://twitter.com/canada?lang=en), [@CanadianPM](https://twitter.com/CanadianPM), [@JustinTrudeau](https://twitter.com/JustinTrudeau?s=20) and [@GovCanHealth](https://twitter.com/govcanhealth?lang=en). After this step, we clean the database by preprocessing sensible information as emails and urls, and droping tweets with adds.

## Explanatory Data Analysis (EDA)
When plotting tweets that mention at least one of the Canadian Government Twitter accounts we find that between February and April 2020, the [@JustinTrudeau](https://twitter.com/JustinTrudeau) account had between 3.0 and 21.4 thousand tweets per day, [@Canada](https://twitter.com/Canada) had between 98 and 470 tweets per day, [@CanadianPM](https://twitter.com/CanadianPM) had between 104 and 1,179 tweets per day, and [@GovCanHealth](https://twitter.com/GovCanHealth) between 30 and 1,182 tweets per day.

<img src="/images/canada-covid_EDA_tweets.png" width="700">

To identify the days with more tweets, removing weekly seasonality, we calculate the Moving Averages with 7-day window, and normalize these averages by account using minimum and maximum number of tweets. In this plot we can identify an increase in number of tweets for all the Canadian Government's Twitter accounts around March 11th, 2020, with a peak of tweets between March 14th and 17th, decreasing from this point on until return to lower levels in mid-April 2020.

<img src="/images/canada-covid_EDA_heatmap.png" width="820">

⭐️ More details of the EDA are available in this [link](https://github.com/vcuspinera/Canada_response_covid/blob/master/src/eda.ipynb).

## Sentiment Analysis

When making sentiment analyses, we must first know what languages we will be considering. For this project, most of the scrapped tweets were written in English (about 85.5% of all tweets), so for the main analysis we used tweets wrote in English. This enhanced the reach of powerful tools like [spaCy](https://spacy.io), [TextBlob](https://textblob.readthedocs.io/en/dev/) and [wordcloud](https://amueller.github.io/word_cloud/), mainly developed for this language.

When comparing word clouds of tweets published before and after the announcement on March 11th, 2020, we found that most used words and their repetitions are very similar among both groups.

<img src="/images/canada-covid_wordcloud.png" width="620">

Wordclouds are always nice but they hardly tell us anything about the trends or distribution in opinions. For our sentiment analysis we made use of spaCy's modules to extract the `polarity` and `subjectivity` of texts.

As wee can see in the plot below, the information conveyed by the downloaded tweets before and after the announcement provide very similar Polarity and Subjectivity curves. While the polarity in both groups is very similar, mainly centered on 0, in both cases it is slightly skewed for positive tweets (however, remember the scale is logarithmic!). In the other hand, when looking at the subjectivity we can notice the huge outlier on the left-hand side when subjectivity equals 0, which tells us that there are many tweets that give no opinion and are only informative, they are not biased to give a positive or negative opinion in any sense whatsoever.

<img src="/images/canada-covid_sentiment_PolarSubject.png" width="750">

Additionally, we perform hypothesis testing polarity and subjectivity on tweets before and after the announcement on sub-samples of tweets, but we couldn't reject that both means of these measures were different.

We also use Time Series to find the Trend of polarity and number of tweets. From this analysis, while the trend in sentiment decrease for the [@Canada](https://twitter.com/canada?lang=en) account, tweets related with the Canadian Prime Minister ([@CanadianPM](https://twitter.com/CanadianPM) and [@JustinTrudeau](https://twitter.com/JustinTrudeau?s=20)) had a positive impact after the announcement. In addition, the [@GovCanHealth](https://twitter.com/govcanhealth?lang=en) had a steady trend in polarity levels.

<img src="/images/canada-covid_sentiment_trend.png" width="750">

Finally, the announcement also impacted in the volume of tweets, as well the actions and reactions of users increasing the number of likes, replies, retweets and quotes.

<img src="/images/canada-covid_sentiment_reactions.png" width="700">

⭐️ [Click here](https://github.com/vcuspinera/Canada_response_covid/blob/master/src/sentiment_analysis.ipynb) to see the complete Sentiment Analysis.

## Final comments
On the analysis we find that the announcement on March 11<sup>th</sup>, and the following announcements of the Government policies related with COVID-19, had an impact in the sentiment of tweets and their volume: 

- __Sentiment__: while the overall sentiment of tweets is positive, the announcement had different effect for the Government accounts. While the effect on [@Canada](https://twitter.com/canada?lang=en) account was a decrease in the average polarity, in the other hand we identify a rise in the positive sentiment of tweets related with the Canadian Prime Minister (which means an increase in the polarity levels of [@CanadianPM](https://twitter.com/CanadianPM) and [@JustinTrudeau](https://twitter.com/JustinTrudeau?s=20) accounts). The [@GovCanHealth](https://twitter.com/govcanhealth?lang=en) account was stable in polarity level before and after the announcement. 
- __Volume__: we observed an increase in the total number of tweets and the average tweets per day. Also, the announcement affected the volume of actions and reactions of users increasing the volume of likes, replies, retweets and quotes.

## Main references

- Government of Canada announcements:
  - March 11, 2020. Prime Minister outlines Canada’s COVID-19 response: [official announce](https://pm.gc.ca/en/news/news-releases/2020/03/11/prime-minister-outlines-canadas-covid-19-response), [video](https://youtu.be/YunI2PNZKxg).
  - March 13, 2020. Prime Minister Trudeau updates Canadians on COVID-19: [official announce](https://pm.gc.ca/en/news/news-releases/2020/03/13/first-ministers-discuss-collective-efforts-address-impact-covid-19), [video](https://youtu.be/u70pUm7xHo0).
  - March 27, 2020. Prime Minister announces support for small businesses facing impacts of COVID‑19: [official announce](https://pm.gc.ca/en/news/news-releases/2020/03/27/prime-minister-announces-support-small-businesses-facing-impacts), [video](https://youtu.be/1o-tV0A87l8).

- [Timeline of the COVID-19 pandemic in Canada](https://en.wikipedia.org/wiki/Timeline_of_the_COVID-19_pandemic_in_Canada?fbclid=IwAR3_8GonnYCyH9lT_aWIYD9AiZEPKQ4pC0yMmY1gwWE1xKu04ksT3ixkNlU), Wikipedia.

⭐️ [Click here](https://github.com/vcuspinera/Canada_response_covid/blob/master/References.md) to access the complete list of references for this project.
