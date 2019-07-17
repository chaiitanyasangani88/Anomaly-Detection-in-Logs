# Anomaly-Detection-in-Logs

Anomaly/ Outlier detection has picked up wind in recent days, owing to its applications in cyber security and server monitoring. This repo explores how to use count vectors and identify anomalies through unsupervised learning.

## About Dataset
The dataset is a logs data from a remote server generated over 15 days. This dataset is created post cleaning and picking only relevant events on which we wish to identify anomalies. 

Columns: 
  - Timestamp of the log
  - Unique identifier of the request
  - User IP from which the request is made
  
## Approach
We create Profiles for User-IP over certain time periods. This time period can vary from few hours to few weeks. The profile can include basic count vectors such as total counts, average unit(day/week/hour) counts to complex network calls vectors such as upload/download ratio based on the use case. 

In this repo we use basic count and frequency vectors. With profiles in hand we can use ML algoriths to identify anomalies.

## ML Approach
Once the feaure space is generated, we use kmeans to cluster and the points which are farther from all clusters combined are considered anomalous. We use sum of squared distances from the centroids in this repo. We use squared distance instead of absolute distance to weigh the outliers more than others(similar to using MAE vs MSE).

While euclidean distance in the feature space is one way to look at it, Isolation forest offers a unique approach to this problem. Isolation trees see the number of splits it take to reach a certain point, the lesser splits required, the more `isolated` the point is and hence, anomalous.
