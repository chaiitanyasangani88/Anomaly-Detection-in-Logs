# Anomaly-Detection-in-Logs

Anomaly/ Outlier detection has picked up wind in recent days, owing to its applications in cyber security and server monitoring. This repo explores how to use count vectors and identify anomalies through unsupervised learning.

## About Dataset
The dataset is a logs data from a remote server generated over 15 days. This dataset is created post cleaning and picking only relevant events on which we wish to identify anomalies. 

Columns: 
  - Timestamp of the log
  - unique identifier of the request
  - User IP from which the request is made
  
## Approach
We create Profiles for User-IP over certain time periods. This time period can vary from few hours to few weeks. The profile can include basic count vectors such as total counts, average unit(day/week/hour) counts to complex network calls vectors such as upload/download ratio based on the use case. 

In this repo we use basic count and frequency vectors. With profiles in had we can use ML algoriths to identify anomalys.

### Kmeans
Once the feaure space is generated, we use kmeans to 
