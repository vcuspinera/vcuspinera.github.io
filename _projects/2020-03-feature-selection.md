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

If you've ever encountered a dataset with a myriad number of features, you know it could be very difficult to work with all of them. Some features may not even be important or relevant and could even cause optimization bias. One approach to this problem is to select a subset of these features for your model. **Feature selection** will reduce both complexity and time training an algorithm, as well as improve the accuracy of your model -- if we select them wisely. However, this is not a trivial task and to that end we have created two **packages** addressing the feature-selection, in **Python** and **R** programming languages.  
$\bigstar$ *In the next links you can access to the original sites of [Python package](https://github.com/UBC-MDS/feature-selection-python/) and [R feature selection package](https://github.com/UBC-MDS/feature-selection-r/).*  

*Authors: Ryan Homer ([ryanhomer](https://github.com/ryanhomer)), Victor Cuspinera ([vcuspinera](https://github.com/vcuspinera)), Derek Kruszewski ([dkruszew](https://github.com/dkruszew)), Jacky Ho ([jackyho112](https://github.com/jackyho112))*  

<center><img src="/images/feature_selection-logo.png" width="200" /></center>

## Features
In this package, four functions are included for feature selection:

- `forward_selection` - This iterative algorithm starts by considering each feature separately to determine the one that results in the model with best accuracy. The process is then repeated iteratively, adding another feature one at a time, again selecting the single feature that gives the best improvement in accuracy. This procedure stops when it is not longer possible to improve the model.

- `recursive_feature_elimination` - The RFE is a model that initially considers all features with the goal of discovering the worst performing feature which is then removed from the dataset. This process is repeated until the desired number of features are attained.

- `simulated_annealing` - Model that selects features by randomly choosing a set of features and determining model performance, then slightly modifying the chosen features randomly and testing to see if the modified feature list has improved model performance. If there is improvement, the newer model is kept, if not, a test is performed to determine if the worse model is still kept based on an acceptance probability that decreases as iterations continue and how worse the newer model performs. This process is repeated for a set number of iterations.

- `variance_thresholding` - Model that select features based on their variances where a threshold, typically a low one, would be set so that any feature with a variance lower than that would be filtered out. Since this algorithm only looks at features without their outputs, it could be used to do feature selection on data related to unsupervised learning.

## Existing Ecosystems

|Function |Python |R    |
|:--------|:-----:|:---:|
|Forward Selection  |No|[Yes](https://www.rdocumentation.org/packages/MXM/versions/0.9.4/topics/Forward%20selection)|
|Recursive Feature Elimination|[Yes](https://scikit-learn.org/stable/modules/generated/sklearn.feature_selection.RFE.html)|[Yes](https://www.rdocumentation.org/packages/caret/versions/6.0-85/topics/rfe)|
|Variance Threshold |[Yes](https://scikit-learn.org/stable/modules/generated/sklearn.feature_selection.VarianceThreshold.html)|No|
|Simulated Annealing|No|No|

# Feature selection package in R

In this section I share the general information of the **R package**. If you are interested in the **Usage** and details of the functions, I encourage you to visit the [original repository for the **R** feature-selection package](https://github.com/UBC-MDS/feature-selection-r).

### Installation

Make sure you have the `devtools` package installed. You can install it as follows.

``` r
#Install development version from Github
install.packages("devtools")
```

Then, install the feature selection package.

``` r
devtools::install_github("UBC-MDS/feature-selection-r")
```

### Dependencies
[R 3.6](https://www.r-project.org/), [dyplr 0.8.0](https://dplyr.tidyverse.org/), [purrr 0.3.0](https://purrr.tidyverse.org/), and [stats 3.6.0](https://stat.ethz.ch/R-manual/R-devel/library/stats/html/00Index.html)

### Documentation
The official documentation is hosted here: <https://ubc-mds.github.io/feature-selection-r>

# Feature selection package in Python

In this section I share the general information of the **Python package**. If you are interested in the **Usage** and details of the functions, I encourage you to visit the [original repository for the **Python** feature-selection package](https://github.com/UBC-MDS/feature-selection-python/).

### Installation

```bash
pip install -i https://test.pypi.org/simple/ --extra-index-url https://pypi.org/simple feature-selection
```

### Dependencies
[python 3.7.5](https://www.python.org/downloads/release/python-375/), [numpy 1.17.4](https://numpy.org/), [pandas 0.25.3](https://pandas.pydata.org/getpandas.html)

### Documentation
The official documentation is hosted on Read the Docs: <https://feature-selection-python-mds.readthedocs.io/en/latest/>
