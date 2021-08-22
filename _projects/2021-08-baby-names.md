---
title: "Choosing a baby name using Python"
author: "Victor Cuspinera"
collection: projects
type: "Personal_projects"
permalink: /projects/2021/baby-names
venue: "GitHub.com"
date: 2021-08-20
location: "Mexico City, Mexico"
tags:
  - Baby names
  - NLP
  - Python
---

Getting a __name for a baby__ is not as trivial as people could think, or at least not for my wife and me. We look for names for our baby girl everywhere and we pick some options. However, I started to wonder if we were looking in the right places and if there could be a way to measure which would be the best name for our daughter. So, I found three databases with names from Spanish and English-speaking countries, analyzed trends and top frequent names, and wrote down a list of all possible names. Finally, I developed an tool that transforms the names using the __International Phonetic Alphabet__ and measures how well a surname sounds with another surname and/or family names in both English and Spanish, by returning a score to make it easier finding possible names for a baby.  
$\bigstar$ *[Click here](https://github.com/vcuspinera/Baby_names) o see the GitHub repository with the complete analysis of this project.*  

*Author: Victor Cuspinera ([vcuspinera](https://github.com/vcuspinera))*  

## Introduction

When we were expecting our first baby girl, during the last five months of the pregnancy, we looked for options of names on different sources as websites and books with popular baby names, websites with international names, asked recommendations between our friends, or even wrote down names of movies and tv series characters. After months of searching names, on early April of 2021 we came with a list of our favourite names for the baby girl. My wife's choices were: **Elisa** and **Macarena**. In my side, I had a wider list: **Aisha, Amanda, Carlina, Gina** and **Victoria**.  

However, we didn't agree in a name for the baby. So, I started to wonder how we could make the best selection of the name for our baby? Which are the most popular names? Is there a way to measure how well a surname sounds combined with the family name?  

## Databases

The first step was to look for names. In our case, because we live in Mexico we were interested on names in Spanish; however, we also were open for a name from an English-speaking country.

For names in Spanish, I found data of the [Statistics National Institute](https://www.ine.es/dyngs/INEbase/es/operacion.htm?c=Estadistica_C&cid=1254736177009&menu=resultados&idp=1254734710990#!tabs-1254736195454) from Spain 🇪🇸 with the most popular 100 names (2002-2019), and names with frequency equal to 20 people or more (2019). In the other hand, for English-speaking countries, I found a couple of databases with popular baby names: one from the U.S. 🇺🇸published by the [Social Security Agency](https://www.ssa.gov/oact/babynames/); and another from state of British Columbia in Canada 🇨🇦, shared by the [Government of B.C.](https://www2.gov.bc.ca/gov/content/life-events/statistics-reports/bc-s-most-popular-baby-names)

## Explanatory Data Analysis (EDA)

When comparing the databases of popular names from Spain, the U.S. and Canada, it would be observed that the number of distinct names were very different among databases. These differences probably could be explained by the structure of the databases because the range of years and their characteristics:

|Country| Number of different names| Number of years| Years | Charactersitics of database|
|:---|:---:|:---:|:---:|:---|
|Spain| 379| 18| 2002-2019| Most popular 100 names |
|B.C., Canada| 4,340| 100| 1920-2019|Names with 5 or more observations |
|USA| 99,444| 140| 1880-2019|Names with 5 or more observations |

While the growth in the average number of people per name is stable for the USA and Canada around 0% level, it is not for Spain, probably because it contains only the 100 most popular names in Spain, compared with the extensive list of names in the USA and Canada data.

<img src="img/baby-names_1_growth_names.png" width="700">

[⭐️ click here](https://github.com/vcuspinera/Baby_names/blob/main/src/analysis.ipynb) to see the notebook with the complete EDA and main analysis.

## Descriptive analysis of our favorite names 

This section I would present the main finds of the descriptive analysis of the perform of our favourite names: Aisha, Amanda, Carlina, Elisa, Gina, Macarena and Victoria, in the names databases from Spain, the U.S. and Canada.

### Spain 🇪🇸

Between the favorite names of our baby, while using the Spain database, the most used name is **victoria** with 59.6 thousand females, followed by **elisa** with 36.3 thousand people, **macarena** with 14.4 thousand, **amanda** with 12.9 thousand, **gina** with 2.3 thousand, **aisha** with 2.0 thousand, and **carlina** with 147 people.

In the other hand, the youngest name is **aisha** with an average age of 9.9 years old, followed by **gina** with an average of 21.4 years old, **amanda** with 24.8 years old, **macarena** with 29.9 years old, **victoria** with 46.7 years old, **elisa** with 48.7 years old, and **carlina** with 61.2 years old.

<img src="img/baby-names_2_spain.png" width="750">

Until now we haven't talk much about the second source from the _Instituto Nacional de Estadística_ from Spain that contain the data of names with frequency equal to or greater than 20 people in 2019. The beauty of this source is that it contains the complete list of names considering also compound names, which was helpful to identify the most common compound names associated with the list of our favorite names, and its average age. For example, the name __maria victoria__ contains the name __victoria__ and it is the most popular name that contain one of our favorite options for our baby girl, however, its average age was 53 years old which means it is a name for older people.

<img src="img/baby-names_3_victoria.png" width="400">

In this sense, in the databases we could find 243 compound names that includes __victoria__, 82 with __elisa__, 31 with __macarena__, 28 with __amanda__, 10 with __gina__, and 3 with __aisha__ and 2 with __carlina__.

The next plot shows the comparison between frequency and average age for all single and compound names that contain one of our seven favorite names for our baby girl.

<img src="img/baby-names_4_favorite.png" width="750">

Finally, the following word cloud presents the compound names with frequency equal to 75 or more observations. While the nodes represent each name, the arrows show the order of connection between names and the darker the arrow, the stronger is the connection between names. For example, the names **maria** and **victoria** are connected in both ways and forms the compound names **maria victoria** and **victoria maria**.

<img src="img/baby-names_5_wordcloud.png" width="550">

### USA 🇺🇸

For the U.S. plot, I am presenting the trend of newborn babies per year from 1950 to 2019 that had any of our seven favorite names.

<img src="img/baby-names_6_usa.png" width="700">

Here we find that while **victoria** has been popular for all years, **gina** became the most popular name in the late 60's and **amanda** in the 80's. The name **elisa** has been in the middle range of our favorite names with values around 500 observations per year, while **aisha** popularity increased from around 10 observations on the 60's to 1,000 on the 70's and became steady on that level. Finally, the names **carlina** and **macarena** are the least popular from our list in records from the U.S.

### BC, Canada 🇨🇦

In this case the following plot presents the trend of newborn babies per year from 1950 to 2019 in British Columbia, Canada, that had any of our favorite names. In this case, the database has information of five from our seven selected names: __victoria__, __elisa__, __amanda__, __gina__ and __aisha__.

<img src="img/baby-names_7_canada.png" width="700">

Similar to the plot from the U.S., here we find that **victoria** has been popular for all years and **amanda** became the most popular name in the 80's and 90's. The popularity of **gina** decreased over time. And finally, the names **elisa** and **aisha** have low records.


## Scoring names using [International Phonetic Alphabet (IPA)](https://en.wikipedia.org/wiki/International_Phonetic_Alphabet)

The last effort of this analysis is to construct a tool that measures how well a surname combines with anothers surname and/or family names.

For this purpose, I transform the names to their Spanish and English phonetic notation using the [IPA](https://en.wikipedia.org/wiki/International_Phonetic_Alphabet), and look for ryhmes in English and Spanish for each comparison between each two strings (names). For example, in the name **maria victoria smith** this function gets the score for the comparison between (1) **maria** and **victoria**, (2) **maria** and **smith**, and (3) **victoria** with **smith**.

In each of this two-strings comparison, I get three scores: Spanish, English and Total. Finally, for complete names with more than two strings I average all scores for Spanish, all scores for English, and all Total scores getting also three final scores (Spanish, English and Total) for a complete name.

[⭐️ click here](https://github.com/vcuspinera/Baby_names/blob/main/src/Names_rhyme.py) to look into the class used to get scores of rhymes of names.  

😅 **_Fun fact:_** when I finally arrived to this point of the analysis on mid-April 2021, my wife already choose a name for our baby girl: **elisa**. From this point, it was on my side to choose if I wanted a compound name for the baby.  

| Name| IPA Spanish| IPA English| Score Spanish| Score English| Score Total|
|:---|:---|:---|:---:|:---:|:---:|
| elisa cuspinera martinez| elisa kuspineɾa maɾtines| əˈlizə kʊzpɪˈnirə mɑrˈtinɛz| 0.0556| 0.3334| 0.1944|

Among the compound female names that includes **elisa** combined with our family names **cuspinera** and **martinez** (this is because in Mexico and Latin America we use two family names), the top of possible second names with higher scores were: aisa, akira, alisa, ariza, corisa, delisa, elfrida, elissa, elvina, elyria, elysia, erisa, isa, jazeera, lisa, liza, louisa, luisa, **macarena**, maeda, magdalena, makita, malina, malinda, malvina, marcelia, marcellina, marchita, margarita, marilda, marina, marquita, martina, martita, mathea, matthea, maurita, mayeda, miera, misa, raisa, riera, risa, shakira, viera.

As you could realize, one of these names is **macarena**. So, as in the movie _Inception_, I felt that my wife implanted on my head the idea of this name and, among the top options of compound names combined with **elisa**, this one was my favorite mainly becase the way it sounds when combining **macarena** and **cuspinera**. Actually, **macarena cuspinera** scores 0.5 in Spanish and 0.6667 in English.  

Finally, we decide that the name of our baby girl would be **elisa macarena cuspinera martinez**, which has an even better score than elisa cuspinera martinez.

| Name| IPA Spanish| IPA English| Score Spanish| Score English| Score Total|
|:---|:---|:---|:---:|:---:|:---:|
| elisa macarena cuspinera martinez| elisa makaɾena kuspineɾa maɾtines| əˈlizə mækəˈrinə kʊzpɪˈnirə mɑrˈtinɛz| 0.1667| 0.4167| 0.2917|

## Final comments

Choosing the name of your baby could be not as easy as people think. The aim of this project was to build a tool that measures how well a complete name would sound assigning a score to make it easier finding possible names for a baby. However, as a tool, this model is only a piece of the puzzle and this could (and should) be complemented with other qualitative variables, for example, meaning of names, regional customs, family traditions, trends and/or other ideas from the future parents.
