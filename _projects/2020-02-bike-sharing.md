---
title: "Bike Sharing Machine Learning Model"
author: "Aman Kumar Garg, Victor Cuspinera-Contreras, Yingping Qian"
collection: projects
type: "Docker"
permalink: /projects/2020/bike-sharing
venue: "MDS-UBC"
date: 2020-02-29
location: "Vancouver, BC, Canada"
tags:
  - Docker
  - MDS student
  - UBC
---

Contributors: Aman Kumar ([amank90](https://github.com/amank90)), Dora Qian ([doraqmon](https://github.com/doraqmon)), and Victor Cuspinera([vcuspinera](https://github.com/vcuspinera)) 

In this project we attempt to build a regression machine learning model using the Random Forest Regressor algorithm which predicts the count of bike rentals based on the time and weather-related information.  

**Introduction**
Demand forecasting is an important aspect for many companies in carrying out their operations. In our case, with the help of demand forecasting, a bike rental company can perform many tasks such as inventory management (no. of bikes), manpower management etc. Such planning will result in making operations efficient and effective. Planning and forecasting can help in facing sudden challenges and problems in a much better way.
Here we ask whether we can predict the count of bike rentals on an hourly basis in order to forecast the future demand for bike rentals given the information shared by Bike Share Company. Also, we want to find strong predictors that can help in predicting the future demand for bike rentals.

**Data**
The dataset we are using to build a machine learning model is the bike-sharing dataset from UCI Machine Learning Repository. It contains both the hourly and daily data about the numbers of bike rentals in Washington, DC between 2011 and 2012. We would use the hourly dataset, which is more complete and have a greater number of observations than the daily dataset. 

The dataset has 1 target and 16 features, including both time and weather-related information for each hour on a specific day. All the features and target are listed below:

1. `instant`: Record index  
2. `dteday`: Date  
3. `season`: Season (**1**:spring, **2**:summer, **3**:fall, **4**:winter)  
4. `yr`: Year (**0**: 2011, **1**:2012)  
5. `mnth`: Month  
6. `hr`: Hour  
7. `holiday`: (**0**: No, **1**: Yes)  
8. `weekday`: Day of the week (starting from **0**: Sunday)  
9. `workingday`: (**0**: No, **1**: Yes)  
10. `weathersit`:  (**1**: Clear, Few clouds, Partly cloudy, Partly cloudy. **2**: Mist + Cloudy, Mist + Broken clouds, Mist + Few clouds, Mist. **3**: Light Snow, Light Rain + Thunderstorm + Scattered clouds, Light Rain + Scattered clouds. **4**: Heavy Rain + Ice Pallets + Thunderstorm + Mist, Snow + Fog)  
11. `temp`: Normalized temperature in Celsius  
12. `atemp`: Normalized feeling temperature in Celsius  
13. `hum`: Normalized humidity  
14. `windspeed`: Normalized wind speed  
15. `casual`: count of casual users  
16. `registered`: count of registered users  
17. `cnt`: count of total rental bikes including both casual and registered  

The dataset was created by Dr. Hadi [@hadi] from the Laboratory of Artificial Intelligence and Decision Support (LIAAD), at the [@uic_repo].

We have performed an explanatory data analysis (EDA), the full report can be found [here](https://github.com/UBC-MDS/DSCI_522_Group_409/blob/master/eda/EDA_summary.md). In this analysis, we built some visualizations to deep dive the data and found the relationships between different variables, as well as the explanatory variables with a higher correlation with the target variable (number of bikes rented). As we can see from Figure 1. below, the demand for bikes increases when the weather is warmer and decreases when the temperatures are lower.

<img src="https://raw.githubusercontent.com/UBC-MDS/DSCI_522_Group_409/master/img/fig_2b_workingday.png" />
