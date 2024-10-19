A clustering method that operates as follows:
- Randomly set *k* centroids (points to calculate distance metrics from)
- Calculate distance metrics from the centroids
- Move the centroid in an effort to form better clusters
This process iterates until the best clusters are found

*k* is a user-input, so one must know how many clusters they want and set *k* to said value.

To optimize the number of clusters, one can plot WCSS values for several *k* values and find the elbow

- Background
	- [[Clustering]]
	- [[Distance Metric]]
	- [[WCSS]]
	- [[Elbow Method]]