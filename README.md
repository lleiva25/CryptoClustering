#  Crypto_Clustering
---------------------------------------------------------------------------------------------
Background
---------------------------------------------------------------------------------------------
In this challenge, you’ll use your knowledge of Python and unsupervised learning to predict if cryptocurrencies are affected by 24-hour or 7-day price changes.

---------------------------------------------------------------------------------------------
Instructions
---------------------------------------------------------------------------------------------
Prepare the Data:
  1. Use the StandardScaler() module from scikit-learn to normalize the data from the CSV file.
  2. Create a DataFrame with the scaled data and set the "coin_id" index from the original DataFrame as the index for the new DataFrame.
  3. The first five rows of the scaled data frame should appear as follows:
     
    <img width="896" alt="Screenshot 2024-01-26 at 9 15 52 AM" src="https://github.com/lleiva25/CryptoClustering/assets/140974405/8666707b-f4d5-43fd-9dbe-0846b3021146">

Find the Best Value for k Using the Original Scaled DataFrame:
  1. Use the elbow method to find the best value for k using the following steps:
             - Create a list with the number of k values from 1 to 11.
             - Create an empty list to store the inertia values.
             - Create a for loop to compute the inertia with each possible value of k.
  2. Create a dictionary with the data to plot the elbow curve.
  3. Plot a line chart with all the inertia values computed with the different values of k to visually identify the optimal value for k.
  4. Answer the following question in your notebook: What is the best value for k?

![image](https://github.com/lleiva25/CryptoClustering/assets/140974405/b472f0d9-8fa5-4e98-91c5-9a91b3762c07)

Cluster Cryptocurrencies with K-means Using the Original Scaled Data:
  1. Use the following steps to cluster the cryptocurrencies for the best value for k on the original scaled data:
            - Initialize the K-means model with the best value for k.
            - Fit the K-means model using the original scaled DataFrame.
            - Predict the clusters to group the cryptocurrencies using the original scaled DataFrame.
  2. Create a copy of the original data and add a new column with the predicted clusters.
  3. Create a scatter plot using hvPlot as follows:
            - Set the x-axis as "PC1" and the y-axis as "PC2".
            - Color the graph points with the labels found using K-means.
            - Add the "coin_id" column in the hover_cols parameter to identify the cryptocurrency represented by each data point.
     
![image](https://github.com/lleiva25/CryptoClustering/assets/140974405/488fb279-c7dc-463c-ba8e-26888308dd65)

Optimize Clusters with Principal Component Analysis:
  1. Using the original scaled DataFrame, perform a PCA and reduce the features to three principal components.
  2. Retrieve the explained variance to determine how much information can be attributed to each principal component and then answer the following question in your notebook:
            - What is the total explained variance of the three principal components?
  3. Create a new DataFrame with the PCA data and set the "coin_id" index from the original DataFrame as the index for the new DataFrame.
  4. The first five rows of the PCA DataFrame should appear as follows:

<img width="425" alt="Screenshot 2024-01-26 at 9 22 31 AM" src="https://github.com/lleiva25/CryptoClustering/assets/140974405/6a2a04e4-b101-43d8-ba41-2af6492f5508">

Find the Best Value for k Using the PCA Data:
  1. Use the elbow method on the PCA data to find the best value for k using the following steps:
           - Create a list with the number of k-values from 1 to 11.
           - Create an empty list to store the inertia values.
           - Create a for loop to compute the inertia with each possible value of k.
  2. Create a dictionary with the data to plot the Elbow curve.
  3. Plot a line chart with all the inertia values computed with the different values of k to visually identify the optimal value for k.
  4. Answer the following question in your notebook:
           - What is the best value for k when using the PCA data?
           - Does it differ from the best k value found using the original data?
     
<img width="704" alt="Screenshot 2024-01-26 at 9 24 41 AM" src="https://github.com/lleiva25/CryptoClustering/assets/140974405/92ede915-f7d2-4118-b3cd-71d3f1324c7f">

Cluster Cryptocurrencies with K-means Using the PCA Data:
  1. Use the following steps to cluster the cryptocurrencies for the best value for k on the PCA data:
           - Initialize the K-means model with the best value for k.
           - Fit the K-means model using the PCA data.
           - Predict the clusters to group the cryptocurrencies using the PCA data.
  2. Create a copy of the DataFrame with the PCA data and add a new column to store the predicted clusters.
  3. Create a scatter plot using hvPlot as follows:
           - Set the x-axis as "price_change_percentage_24h" and the y-axis as "price_change_percentage_7d".
           - Color the graph points with the labels found using K-means.
           - Add the "coin_id" column in the hover_cols parameter to identify the cryptocurrency represented by each data point.
  4. Answer the following question:
           - What is the impact of using fewer features to cluster the data using K-Means?
