# KMeans-Clustering
Two methods of K-means clustering are implemented in this project including basic and smart K-means clustering. 

### 1. Basic Clustering Algorithm
First, k random points are chosen. These chosen data are actually the centers of the clusters which are called centroids. In the second step, the distances between all points and centroids must be calculated. Among the distances, we assign the label or index of a centroid that has the least distance value. After assigning labels to all the points, it's time to update the centroids. For updating the centroids as it's obvious from the name of the algorithm, the new centroids in each cluster will be the results of meaning or averaging the points that cluster. 

### Implementation
* We plot the loss values resulting from the implementation for different values of clusters (including 5, 10, and 20) for 20 iterations. Observing the plotted graphs, we can see that the convergence value in k = 20 is less than that in k = 5 or k = 10. It's obvious that we need a model which has a better performance and it means that its final loss value is less than others. So, in this case, k = 20 is better than the two other states.

* We define a ratio that can make a reasonable comparison between the outer distance and the inner distance of clusters. This ratio can be calculated as follows:

![image](https://user-images.githubusercontent.com/125180530/218331140-986d1c36-312f-45a4-8e56-cade375e12bd.png)

#### Outer Distance: The summation of distances from each point to the centroids that this point is not in the corresponding clusters. 

#### Inner Distance: The summation of distances from each point to the centroid that this point is in the corresponding cluster. 


For all three cases of k, we plot the ratio values vs iterations. The ratio values for k = 20 are more than the other two cases. 

### Conclusion
The main goal of the clustering algorithms is to reduce intracluster distances and increase intercluster distances. First of all, we tell a brief definition of these two distances:

####  Intracluster Distance: Intracluster distance is the distance between two objects belonging to the same cluster.
####  Intercluster Distance: Intercluster distance is the distance between two objects belonging to two different clusters.

![image](https://user-images.githubusercontent.com/125180530/218331919-d6622583-cb0a-4c14-a7fa-c5989be7520b.png)

If a clustering algorithm makes clusters so that the Intercluster distance between different clusters is more and the Intracluster distance of the same cluster is less, then we can tell that it is a good clustering algorithm. So, by the definition of the mentioned ratio and the case in which we try to reduce the intracluster distance and increase the intercluster distance, this ratio converges to 1. So, the better the algorithm, the nearer the value of the ratio to 1. So again, in this case, we can see that k = 20 is the best. 

Another graph that will be useful to evaluate is the graph corresponding to the mean values of the cost function. Before analyzing this graph we define elbow point:

### Elbow Method
In cluster analysis, the elbow method is a heuristic used in determining the number of clusters in a data set. The method consists of plotting the explained variation as a function of the number of clusters and picking the elbow of the curve as the number of clusters to use. 

We can see an elbow point in the graph. At this point, we have the optimal and best value for k in K-means clustering which is k = 10.

### 2. Smart Clustering Algorithm
For this algorithm, we are given a file named "Constraint". By reading this file, we save the indexes of data in this file in two variables 'di' and 'dj'. We assign their labels which show whether they are in the same cluster or not, in the 'state' variable. 

### Implementation
The implementation of this algorithm is just like the previous one with a little difference. After the primary clustering of all data, we have to evaluate the validation or correctness of all the constraints given in the mentioned file. If any constraint is correct, then we do nothing and won't alter any data's cluster but in case of detecting any invalidation in each constraint, we have to change the data's cluster to the right one. 

Just like the previous method, we plot the graphs of the cost function and ratio for different values of k and for using three different numbers of constraints (20, 40, and 60). Conclusions can be made in the same way that is done before 
