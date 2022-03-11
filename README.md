# Anomaly-Detection

Problem:
Along with this document you will have received a dataset containing behavioral data for a few cows. The file for every cow contains a list of floats that can be casted to a
matrix of shape (6000, 4). The first dimension indexes time and, in particular, a range of time lasting for 15 minutes. Therefore, every file represents around 2 months of that
cow’s life; there are no gaps in it. The second dimension indexes a cow behavior, with every value within the matrix representing the percentage of the time (between 0 and
1) the cow spent doing a particular behavior during that 15-minute range. The cow behaviors are indexed in the following order:
• Doing nothing.
• Eating.
• Ruminating.
• Walking.
Cows do not really do anything else apart from these four things (they sleep only for 10 minutes a day!), so treat these items as mutually-exclusive and exhaustive. Even if
your knowledge of cow biology is non-existent, there is one fair assumption you can make: if the usual behavioral pattern of a cow gets seriously altered, that is probably
not good. This is the case with human sleep cycles and eating times, for instance. Detecting these anomalies fast enough could be very useful for dairy farmers, since they could signal serious illnesses. 

Solution:

Code 1- Visualization:
First I created some visualization to gain initial insight on data.  However, no specific clustering or anomaly is visible through visualization.

Code 2- Clustering – kmeans:
As first and simple solution, I developed a k-means model to group the data. Then by calculating the distance of each data point to its cluster's centroid, I assumed that outliers are those data points whose distances are greater than 90 percentile of all distances.
Clustering has some drawbacks which is not proper to this problem. The most important negative point is that it does not consider time dependencies.

Code 3- LSTM Autoencoder:
As second and more complex approach, I developed a lstm auto encoder. Additional notes on this model are available on the code file (please check the comments on the file).

