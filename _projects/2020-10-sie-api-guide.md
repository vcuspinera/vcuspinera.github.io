---
title: "Guide and tips to use SIE API"
author: "Victor Cuspinera"
collection: projects
type: "Guide"
permalink: /projects/2020/sie-api-guide
venue: "MDS-UBC GitHub"
date: 2020-10-26
location: "Mexico City, Mexico"
tags:
  - R
  - SIE
  - API
  - Banxico
---

The Economic Information System, known as SIE, is published by the Banco de Mexico to share the archive of different economic databases. This Central Bank has developed an API that allows developers, analysts and researchers to consult these time series.  The purpose of this project is serve as a guide to use SIE's API with the tools of the **`siebanxicor` R-package** developed by Banco de Mexico, as well as a custome function developed to easily explore the time series.  
$\bigstar$ *[Click here](https://github.com/vcuspinera/SIE_API_guide) to look at the complete guide, tips and examples to use the SIE API in the GitHub repository.*  

*Author: Victor Cuspinera ([vcuspinera](https://github.com/vcuspinera))*  

```diff
# ⚠️ The views and conclusions presented in this Repository are exclusively  #
#     the responsibility of the author and do not necessarily reflect those  #
#     of Banco de Mexico.                                                    #
```

## Before starting

### Request a token
The first step to use the SIE API is to get an access token, which is a 64-alphanumeric string, which would be required to use the API. You can get it in [this link](https://www.banxico.org.mx/SieAPIRest/service/v1/token).  

### SIE series

[⭐️ Here](https://www.banxico.org.mx/SieAPIRest/service/v1/doc/catalogoSeries) you could find the complete catalogue of the SIE's series published by Banco de Mexico.

### Installation of R-package
Banco de Mexico developed a package for R called `siebanxicor` for to automatically retrieve economic databases published in the SIE. You can install this package by running the next line:

```{r}
install.packages("siebanxicor")
```

More details of the `siebanxicor` R-package can be found [here](https://cran.r-project.org/web/packages/siebanxicor/siebanxicor.pdf).

## Features of `siebanxicor`

The `siebanxicor` R-package has five utility functions to retrieve information from the databases published by the Mexican Central Bank: 

- `setToken` - while the Bnx-Token is the key to access SIE API, the `setToken` function is the knob that opens the channel to and connects to this API. This utility function should be called before any other function from the siebanxicor package.  

- `getSeriesData` - requests the time series data from the SIE, up to 100 series at a time. It returns a vector with the requested information.  

- `getSeriesMetadata` - retrieves [metadata](https://en.wikipedia.org/wiki/Metadata) for the requested series.  

- `getSerieDataFrame` - allows to get a data.frame from <u>only one</u> time series of the vector returned by the `getSeriesData` utility function.  

- `getSeriesCurrentValue` - requests the time series data from the SIE, up to 100 series at a time, returning a data.frame with only the <u>last value</u> of the requests time series.  

_Note: In some cases, to use one of these functions you should previously use another(s) of the mentioned functions; for example, to use `getSeriesMetadata` you should previously call `setToken` and `getSeriesData`._  

Additionally, I have created a custome support function that can be found in the __src__ folder of this repo, for helping users to easily explore the time series:  

- `SIE_function` - when giving the names of the code of different time series, it automatically prints and saves the plot of this series, prints the metadata, and returns the data in a tidy data frame format.

[👉 Click here](https://github.com/vcuspinera/SIE_API_guide/blob/main/src/SIE_function_examples.pdf) to access to the complementary document developed to show additional examples of this custome function used in different contexts with time series published in the SIE by Banco de Mexico.

## Documentation
The official documentation by Banco de Mexico related with the SIE can be found in the next sites:

| Official Websites|
|:----------|
|📁 [SIE](https://www.banxico.org.mx/SieInternet/defaultEnglish.do) |
|🛠 [SIE API](https://www.banxico.org.mx/SieAPIRest/service/v1/?locale=en)|
|🔎 [Series Catalogue](https://www.banxico.org.mx/SieAPIRest/service/v1/doc/catalogoSeries)|
|📦 [`siebanxicor` R-Package](https://cran.r-project.org/web/packages/siebanxicor/siebanxicor.pdf)|
|📌 [Banco de Mexico](https://www.banxico.org.mx/indexen.html)|

Additionally, the links of to the complete guide of the SIE API, as well as diverse examples can be found in the following links:

| SIE API guide sites|
|:----------|
|📖 [Complete guide and tips to use SIE API](https://github.com/vcuspinera/SIE_API_guide) |
|📊 [Examples to use the `sie_function`](https://github.com/vcuspinera/SIE_API_guide/blob/main/src/SIE_function_examples.pdf)|
|💰 [Analysis of Banknotes in Circulation](https://github.com/vcuspinera/SIE_API_guide/blob/main/src/SIE_banknotes_in_circulation.pdf)|
