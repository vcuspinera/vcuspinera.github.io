---
title: "Guide and tips to use SIE API"
author: "Victor Cuspinera"
collection: projects
type: "Guide"
permalink: /projects/2020/sie-api-guide
venue: "MDS-UBC GitHub"
date: 2020-11-06
location: "Mexico City, Mexico"
tags:
  - R
  - SIE
  - API
  - Banxico
---

Banco de Mexico publishes the archive of national economic databases through the Economic Information System, known as **SIE**.  Also, this Central Bank has developed an **API** that allows Developers, Analysts and Researchers to consult automatically these time series.  To complement this effort, as a personal project, I prepared a guide to disclosure the SIE API, explaining how to retrieve information using the **`siebanxicor` R package** developed by Banco de Mexico, as well as a custom function to explore the selected series and a Dashboard to look into currency time series.  
$\bigstar$ *[Click here](https://github.com/vcuspinera/Banxico_SIE_API_guide) to look the GitHub repository with the complete guide, tips and dashboard to use the SIE API with R.*  

*Author: Victor Cuspinera ([vcuspinera](https://github.com/vcuspinera))*  


```diff
# ⚠️ The views and conclusions presented in this project are exclusively #
#     the responsibility of the author and do not necessarily reflect    #
#     those of Banco de Mexico.                                          #
```

## Before starting

### Request a token
The first step to use the SIE API is to get an access token, which is a 64-alphanumeric string, which would be required to use the API. You can get it in [this link](https://www.banxico.org.mx/SieAPIRest/service/v1/token).  

### SIE series

⭐️ [Here](https://www.banxico.org.mx/SieAPIRest/service/v1/doc/catalogoSeries) you will find the complete catalogue of the SIE's series published by Banco de Mexico.

### Installation of R package
Banco de Mexico developed a package for R called `siebanxicor` for to automatically retrieve economic databases published in the SIE. You can install this package by running the next line:

```{r}
install.packages("siebanxicor")
```

More details of the `siebanxicor` R package can be found [here](https://cran.r-project.org/web/packages/siebanxicor/siebanxicor.pdf).

## Features of `siebanxicor`

The `siebanxicor` R package has five utility functions to retrieve information from the databases published by the Mexican Central Bank: 

- `setToken` - while the Bnx-Token is the key to access SIE API, the `setToken` function is the knob that opens the channel to and connects to this API. This utility function should be called before any other function from the siebanxicor package.  

- `getSeriesData` - requests the time series data from the SIE, up to 100 series at a time. It returns a vector with the requested information.  

- `getSeriesMetadata` - retrieves [metadata](https://en.wikipedia.org/wiki/Metadata) for the requested series.  

- `getSerieDataFrame` - allows to get a data.frame from <u>only one</u> time series of the vector returned by the `getSeriesData` utility function.  

- `getSeriesCurrentValue` - requests the time series data from the SIE, up to 100 series at a time, returning a data.frame with only the <u>last value</u> of the requests time series.  

_Note: In some cases, to use one of these functions you should previously use another(s) of the mentioned functions; for example, to use `getSeriesMetadata` you should previously call `setToken` and `getSeriesData`._  

Additionally, I have created a custom support function that can be found in the __src__ folder of the [API SIE Guide repository](https://github.com/vcuspinera/Banxico_SIE_API_guide), to help Analysts and Researchers to easily explore the time series:  

- `sie_function` - when giving the names of the code of different time series, it automatically prints and saves the plot of this series, prints the metadata, and returns the data in a tidy data frame format.

⭐️ [Click here](https://github.com/vcuspinera/Banxico_SIE_API_guide/blob/main/src/SIE_function_examples.pdf) to access to the complementary document developed to show additional examples of this custom function used in different contexts with time series published in the SIE by Banco de Mexico.

## Dashboard
To complement this effort, I built a Dashboard that focus on Mexican Banknotes and Coins exploring currency time series from SIE API with the option of saving the database of the selected series, in wide or tidy format.  

[![](https://raw.githubusercontent.com/vcuspinera/Banxico_SIE_API_guide/main/img/sie_app%20-%20sketch.png)](https://github.com/vcuspinera/Banxico_SIE_API_guide/tree/main/sie_app)  
⭐️ [Click here](https://github.com/vcuspinera/Banxico_SIE_API_guide/tree/main/sie_app) for details and instructions to run the app.

## Documentation
The official documentation by Banco de Mexico related with the SIE can be found in the next sites:

| Official Websites|
|:----------|
|📁 [SIE](https://www.banxico.org.mx/SieInternet/defaultEnglish.do) |
|🛠 [SIE API](https://www.banxico.org.mx/SieAPIRest/service/v1/?locale=en)|
|🔎 [Series Catalogue](https://www.banxico.org.mx/SieAPIRest/service/v1/doc/catalogoSeries)|
|📦 [`siebanxicor` R package](https://cran.r-project.org/web/packages/siebanxicor/siebanxicor.pdf)|
|📌 [Banco de Mexico](https://www.banxico.org.mx/indexen.html)|

Additionally, the links of to the complete guide of the SIE API, as well as diverse examples can be found in the following links:

| SIE API guide sites|
|:----------|
|📖 [Complete guide and tips to use SIE API](https://github.com/vcuspinera/Banxico_SIE_API_guide) |
|🕹 [Custom Dashboard with SIE API Currency series](https://github.com/vcuspinera/Banxico_SIE_API_guide/tree/main/sie_app)|
|📊 [Examples to use the `sie_function`](https://github.com/vcuspinera/Banxico_SIE_API_guide/blob/main/src/SIE_function_examples.pdf)|
|💰 [Analysis of Banknotes in Circulation](https://github.com/vcuspinera/Banxico_SIE_API_guide/blob/main/src/SIE_banknotes_in_circulation.pdf)|
