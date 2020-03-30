---
title: "Bike Sharing Machine Learning Model"
collection: projects
type: "Docker"
permalink: /projects/2020/bike-sharing
venue: "MDS-UBC"
date: 2020-02-29
location: "Vancouver, BC, Canada"
---

Creators: Aman Kumar Garg, Victor Cuspinera-Contreras, Yingping Qian

**About**
Here we attempt to build a regression machine learning model using the Random Forest Regressor algorithm which predicts the count of bike rentals based on the time and weather-related information. The main predictive research question is "Given the information shared by Bike share company, can we predict the count of bike rentals on hourly basis in order to forecast the future demand of bike rentals?"  

Our final model performed fairly well on an unseen test data set, with the mean square error of 70.39 and a visually linear relationship between actual and predicted values. However, the variance of predicted values becomes larger as the actual count of bike rentals increases, which indicates there are incorrectness in the model when the prediction is large. Thus we recommend continuing study to improve our machine learning model.  

The dataset we are using to build a machine learning model is the bike-sharing dataset from UCI Machine Learning Repository. It contains both the hourly and daily data about the numbers of bike rentals in Washington, DC between 2011 and 2012. We would use the hourly dataset, which is more complete and have a greater number of observations than the daily dataset. The dataset has 1 target and 16 features, including both time and weather-related information for each hour on a specific day.  

The dataset was created by Dr. Hadi (Fanaee-T 2013) from the Laboratory of Artificial Intelligence and Decision Support (LIAAD), at the (UCI Machine Learning Repository 2017) and can be found here.  