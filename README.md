# Customer Segmentation in E-commerce

This project focuses on customer segmentation in an e-commerce dataset. The goal is to divide the customers into distinct groups based on their behavior and characteristics. The analysis aims to uncover patterns and insights that can help improve marketing strategies and personalize the customer experience.


## Dataset

The dataset used in this project is sourced from an e-commerce company and contains information about customer interactions and purchases. The dataset includes the following columns:

- `Cust_ID`: Customer_ID in that particular e-commerce website (dropped during preprocessing).
- `Gender`: The gender of the customer.
- `Orders`: The number of orders made by each customer in total.
- `Brand1`, `Brand2`, ..., `BrandN`: The number of searches made by each customer for different brands.
- `Total_Search`: Total number of search made by each customer across brands (added during analysis).
- `Cluster`: The assigned cluster label for each customer (added during analysis).


## Data Preprocessing
The code begins by importing necessary libraries and loading the dataset into a Pandas DataFrame. It performs some initial data exploration by checking the shape of the dataset, identifying missing values, and removing duplicates.

Next, the categorical variable "Gender" is encoded into numerical values using one-hot encoding, as K-means clustering requires numerical inputs.

Outliers in the dataset are handled by applying clipping, which caps the values at a specified quantile without removing the instances.


## Determining the Optimal Number of Clusters
The code uses the elbow method, silhouette score, Calinski-Harabasz score, and Davies-Bouldin score to determine the optimal number of clusters. It calculates these metrics for a range of cluster numbers from 2 to 10 and visualizes the results using plots.

Based on the metrics, the code selects the number of clusters with the best scores, which in this case is 2 clusters.

<br>

<br>

<div align="center">
  <img src="https://github.com/Nirmal-Data-Scientist/E-Com-Customer-Segmentation/assets/123751119/da3da232-5124-40e3-a961-dfab596082db" alt="Visualization">
</div>

<br>

<br>

<div align="center">
  <img src="https://github.com/Nirmal-Data-Scientist/E-Com-Customer-Segmentation/assets/123751119/ce392b8f-ebf0-4198-97a2-f3bcc63b365a" alt="Visualization">
</div>

## Clustering and Visualization
Using the optimal number of clusters, the code performs K-means clustering on the preprocessed dataset. It assigns cluster labels to each data point.

The code then visualizes the clusters by plotting a scatter plot of "Orders" versus "Jordan" variables, with each cluster represented by a different color.

Furthermore, the code displays the count of customers in each cluster and the total number of searches and orders made by customers in each cluster. It also presents gender-specific information within each cluster.


## Interpretation of Results
The analysis reveals two distinct customer clusters based on search behavior and purchase patterns. Here are some key insights:

    Among 30000 customer
    1. Cluster 0 has 12432 customers (Very Low past orders but done most searches)
    Cluster 1 has 9128 customers (Very High past orders and average searches)
    Cluster 2 has 8440 customers (Average past orders and average searches)
    2. Cluster 0 has done most number of searches with 81477 searches.
    Cluster 2 has least number of searches with 60093 searches followed by cluster 1 with 64573 searches.


## Conclusion
The customer segmentation analysis using K-means clustering provides valuable insights into the search behavior and purchase patterns of e-commerce customers. The identified clusters can be used to tailor marketing strategies, improve customer targeting, and personalize recommendations to increase sales and customer satisfaction.
