# Project: Predictive Analytics Capstone

# Task 1: Determine Store Formats for Existing Stores

1. What is the optimal number of store formats? How did you arrive at that number?
    The optimal number of store formats is three. The conducted steps started by getting the
    AR and CH indices (via the K-Centroids Diagnostics as shown below) and thereby the K-
    Means are selected methodology.

```
The highest AR of 0.6936 and CH of 29.47 indices are the results of a three-cluster
solution.
```

2. How many stores fall into each store format?
    By conducting a cluster analysis (using the K-Means method), the number of stores into
    each store format is as follows:
    Cluster 1 = 23 stores
    Cluster 2 = 29 stores
    Cluster 3 = 33 stores

```
Hence each one of the existing stores was associated with the appropriate cluster.
```
3. Based on the results of the clustering model, what is one way that the clusters differ from
    one another?
    One way that the clusters differ from one another is the average total sales. As shown in
    the visualization below. Other differences are shown in the second graph below:


4. Please provide a Tableau visualization (saved as a Tableau Public file) that shows the
    location of the stores, uses color to show cluster, and size to show total sales.
    Here is the link:
    https://public.tableau.com/profile/mohammed.assiri5000#!/vizhome/Task1_79/Task1?publish=yes


# Task 2: Formats for New Stores

1. What methodology did you use to predict the best store format for the new stores? Why
    did you choose that methodology? (Remember to Use a 20% validation sample with
    Random Seed = 3 to test differences in models.)
    As a non-binary classification problem, three distinct methodologies can be used.
    However, to determine the most appropriate one, the following steps were followed.
    First, data preparation of existing and new stores to include demographic data. Then,
    model construction of three namely, decision tree model, forest model, and boosted
    model. A 20% validation sample was ensured.

```
The comparison of the three model is shown in the table below:
```
```
Hence, it can be concluded that, while all model performed equally regarding the
validation sample, the boosted model was the most appropriate to use as it has the
highest F1 score than the other two models.
```
2. What format do each of the 10 new stores fall into? Please fill in the table below.

```
Store Number Segment
S0086 3
S0087 2
S0088 1
S0089 2
S0090 2
S0091 1
S0092 2
S0093 1
S0094 2
S0095 2
```

# Task 3: Predicting Produce Sales

1. What type of ETS or ARIMA model did you use for each forecast? Use ETS(a,m,n)
    or ARIMA(ar, i, ma) notation. How did you come to that decision?

```
In the next table, both ETS and ARIMA models are discussed.
```
```
In this ETS, the error is irregular (i.e.
multiplicatively(M)), the trend is not
clear (i.e. none (N)), and the
seasonal is increasing (i.e.
multiplicatively(M))
```
```
Therefore, ETS is
ETS(M, N, M) model
```
```
After non-seasonal and seasonal
differencing, the configuration is as
follows:
```
- Non-seasonal:
    o AR = 0
    o I = 0
    o MA = 2
       § since ACF is negative at
          lag-1 and hence MA term
          should be used
- seasonal:
    o AR = 0
    o I = 1
    o MA = 0
       § since differencing is one
          seasonal
- m = 12
    (as the sample)

```
Hence,
ARIMA(0,1,2)(0,1,0) 12 model
```
```
ACF
```
(^) _and PACF_
(^) _of ARIMA
(non_

_- seasonal)_

```
ACF
```
(^) _and PACF_
(^) _of ARIMA
(seasonal)_


```
Now, the comparison between both models is as follows:
```
```
It can be noticed that ETS performs overly better than ARIMA with respect to the
sample. Therefore, the forecast should be ETS(M, N, M).
```
2. Please provide a Tableau Dashboard (saved as a Tableau Public file) that includes a
    table and a plot of the three monthly forecasts; one for existing, one for new, and one
    for all stores. Please name the tab in the Tableau file "Task 3".

```
ACF and PACF of ARIMA after differencing
```

Here is the link:

https://public.tableau.com/profile/mohammed.assiri3979#!/vizhome/Task3v3_0/Task3?publish=yes


