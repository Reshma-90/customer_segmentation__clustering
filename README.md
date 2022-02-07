# Customer_Segmentation_Clustering
This repository contains code for identifying target customers to provide bank promotional offers based on their credit card usage.
# Head of the dataset
![image](https://user-images.githubusercontent.com/95558910/152810875-802661e9-ba28-49bf-a7c0-2e70f3a131ce.png)
# Data Description
![image](https://user-images.githubusercontent.com/95558910/152811141-4183840f-8c84-4adb-9213-754700d24a4f.png)
# EDA
- All preprocesseing steps like checking missing values,duplicate values,random error checking,outliers checking were performed and necessary steps taken.
- An Exploratory Data Analysis were performed on the dataset by doing univariate,bivariate and multivariate analysis.
- From EDA some insights were noted down.
# Scaling
- Distance based algorithms are affected by the scale of the variables.This will impact the performance of all distance based model as it will give higher weightage to variables which have higher magnitude.To overcome this problem,all the variables can be brought down to the same scale before clustering.
- standard scaler is used here which computes the z-score value of each value of every column with mean 0 and standard deviation 1.
# Hierarchical Clustering
- Dendrogram and linkage module were imported.
- Ward linkage is used here.
## Dendrogram
![image](https://user-images.githubusercontent.com/95558910/152812488-c57e6ec7-2343-4cf8-a73a-2c464c31c902.png)
## Cutting the Dendrogram with suitable clusters
It can be visualize from the dendrogram that the blue line has more distance hence it can be cut with threshold distance 3.5(assumed here).
![image](https://user-images.githubusercontent.com/95558910/152812916-3e5a3a84-4f84-46a0-8d03-e8d318cd8966.png)
## Appending clusters to original dataset
![image](https://user-images.githubusercontent.com/95558910/152813193-a201b67f-dc36-4a02-b4a2-74dfa6d6cc42.png)
## Cluster Frequency
![image](https://user-images.githubusercontent.com/95558910/152813424-c2e8a13f-0f91-4ca3-a002-c51b91edabd8.png)
- Cluster 1: Targeted customers to give promotional offer(High credit limit,high monthly spending,have good current balance in bank,spends a good amount in single shopping)
- Cluster 2: Least targeted customers (Less monthly spending,customers have less current balance,less credit limit offered to this category)
## Visualising clusters
![image](https://user-images.githubusercontent.com/95558910/152813693-f6ab2157-1e1d-48b1-ab16-09c1c5e1c05a.png)
- Black colored dots shows cluster 1(Targeted customers)
- Yellow colored dots shows cluster 2(Least targeted customers)
# Applying K-Means clustering on scaled data and finding optimum clusters
- K value considered in range of 1 to 6 and corresponding WSS values were compared.
- Elbow criterion is used to find optimum number of clusters.

![image](https://user-images.githubusercontent.com/95558910/152814517-d30bb2e2-4760-41e5-9a75-ca6beb39bc56.png)


- The elbow criterion doesn't always work well. In that case silhouette score method can be tried for determining the optimal k.
- Silhouette Coefficient or silhouette score is a metric used to calculate the goodness of a clustering technique. Its value ranges from -1 to 1.

1: Means clusters are well apart from each other and clearly distinguished.

0: Means clusters are indifferent, or we can say that the distance between clusters is not significant.

-1: Means clusters are assigned in the wrong way.
- It is found that silhouette score is better for 2 clusters.So, final clusters numbers selected is 2.
## Cluster profiling
![image](https://user-images.githubusercontent.com/95558910/152815414-e847c040-30ef-4789-bd68-ce81bbf9ebe8.png)
