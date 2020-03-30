---
title: "Feature selection - R and Python packages"
author: "Ryan Homer, Victor Cuspinera, Derek Kruszewski, Jacky Ho"
collection: projects
type: "Packages"
permalink: /projects/2020/feature-selection
venue: "MDS-UBC GitHub"
date: 2020-03-26
location: "Vancouver, BC, Canada"
tags:
  - R
  - Python
  - Packages
  - MDS student
  - UBC
---

If you've ever encountered a dataset with a myriad number of features, you know it could be very difficult to work with all of them. Some features may not even be important or relevant and could even cause optimization bias. One approach to this problem is to select a subset of these features for your model. **Feature selection** will reduce both complexity and time training an algorithm, as well as improve the accuracy of your model -- if we select them wisely. However, this is not a trivial task and to that end we have created two **packages** addressing the feature-selection, in **Python** and **R programming languages**.  
*In the next links you can access to the original sites of [Python package](https://github.com/UBC-MDS/feature-selection-python/) and [R feature selection package](https://github.com/UBC-MDS/feature-selection-r/).*  

*Authors: Ryan Homer ([ryanhomer](https://github.com/ryanhomer)), Victor Cuspinera ([vcuspinera](https://github.com/vcuspinera)), Derek Kruszewski ([dkruszew](https://github.com/dkruszew)), Jacky Ho ([jackyho112](https://github.com/jackyho112))*  

<center><img src="/images/feature_selection-logo.png" width=150/></center>

## Features
In this package, four functions are included for feature selection:

- `forward_selection` - Forward Selection for greedy feature selection. This iterative algorithm starts by considering each feature separately to determine the one that results in the model with best accuracy. The process is then repeated iteratively, adding another feature one at a time, again selecting the single feature that gives the best improvement in accuracy. This procedure stops when it is not longer possible to improve the model.

- `recursive_feature_elimination` - Recursive Feature Elimination (RFE) for greedy feature selection. The model initially considers all features with the goal of discovering the worst performing feature which is then removed from the dataset. This process is repeated until the desired number of features are attained.

- `simulated_annealing` - Perform simmulated annealing to select features by randomly choosing a set of features and determining model performance, then slightly modifying the chosen features randomly and testing to see if the modified feature list has improved model performance. If there is improvement, the newer model is kept, if not, a test is performed to determine if the worse model is still kept based on an acceptance probability that decreases as iterations continue and how worse the newer model performs. The process is repeated for a set number of iterations.

- `variance_thresholding` - Select features based on their variances. A threshold, typically a low one, would be set so that any feature with a variance lower than that would be filtered out. Since this algorithm only looks at features without their outputs, it could be used to do feature selection on data related to unsupervised learning.

# Existing Ecosystems

|Feature|Python |R    |
|:------|:-----:|:---:|
|Forward Selection  |No|[Yes](https://www.rdocumentation.org/packages/MXM/versions/0.9.4/topics/Forward%20selection)|
|Recursive Feature Elimination|[Yes](https://scikit-learn.org/stable/modules/generated/sklearn.feature_selection.RFE.html)|[Yes](https://www.rdocumentation.org/packages/caret/versions/6.0-85/topics/rfe)|
|Variance Threshold |[Yes](https://scikit-learn.org/stable/modules/generated/sklearn.feature_selection.VarianceThreshold.html)|No|
|Simulated Annealing|No|No|

