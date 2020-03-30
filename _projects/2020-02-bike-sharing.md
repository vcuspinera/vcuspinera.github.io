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
  - Rental bikes
  - Docker
  - MDS student
  - UBC
---

Demand forecasting is an important aspect for many companies in carrying out their operations. In this project we analyze the bike-sharing dataset from [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/bike+sharing+dataset), and build a regression learning machine model using the **Random Forest Regressor** algorithm to **predict the count of bike rentals** based on time and weather-related information. For this project we use **Docker** making it easy to replicate the analysis.
[Click here](https://github.com/UBC-MDS/DSCI_522_Group_409) to look at the original GitHub repository of this project.  

*Authors: Aman Kumar ([amank90](https://github.com/amank90)), Dora Qian ([doraqmon](https://github.com/doraqmon)), and Victor Cuspinera ([vcuspinera](https://github.com/vcuspinera))*  

### Dataset
The data that we use to build the model comes from the bike-sharing dataset was created by Dr. Hadi from [LIAAD](http://www.liaad.up.pt) and shared in the [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/bike+sharing+dataset). 

The dataset contains the hourly information about the numbers of bike rentals in Washington, DC between 2011 and 2012. It has 17 variables, standing out:  

1. `cnt` count of total rental bikes including both casual and registered  
2. `season`: Season (**1**:spring, **2**:summer, **3**:fall, **4**:winter)  
3. `dteday`: Date
4. `hr`: Hour  
5. `holiday`: (**0**: No, **1**: Yes)  
6. `weekday`: Day of the week (starting from **0**: Sunday)  
7. `workingday`: (**0**: No, **1**: Yes)  
8. `weathersit`:  (**1**: Sunny or partly cloudy. **2**: Mist or cloudy. **3**: Light rain or snow. **4**: Heavy rain, thunderstorm or snow)  
9. `temp`: Normalized temperature in Celsius  
10. `hum`: Normalized humidity  
11. `windspeed`: Normalized wind speed  


### Explanatory Data Analysis (EDA) 

In this analysis, we built some visualizations to deep dive the data and found the relationships between different variables, as well as the explanatory variables with a higher correlation with the target variable (number of bikes rented). The full EDA reort can be found [here.](https://github.com/UBC-MDS/DSCI_522_Group_409/blob/master/eda/EDA_summary.md)  

Among our finds, we observe that the demand for bikes increases when the weather is warmer and decreases when the temperatures are lower. 

<img src="https://raw.githubusercontent.com/vcuspinera/DSCI_522_Group_409/master/img/fig_2b_workingday.png" />
Figure 1. Analysis of temperatures by workingday  

The day of week and hour of the day clearly affects the count of bike rental. Also, people rent these bikes mainly for work and school on weekdays showing the peak of the demand in two times of the day. Besides, people use rental bikes between 11 am and 4 pm during weekends.  

<img src="https://raw.githubusercontent.com/vcuspinera/DSCI_522_Group_409/master/img/fig_3_hr.png" />
Figure 2. Analysis per hour and weekday  

The correlation matrix between features, including the target variable, is shown below.  
<img src="https://raw.githubusercontent.com/vcuspinera/DSCI_522_Group_409/master/img/fig_5_corr.png" />
Figure 3. Correlation matrix  


### Results
  