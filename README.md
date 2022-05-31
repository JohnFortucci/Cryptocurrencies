# Introduction

We have been assked to create a report that includes what cryptocurrencies are on the trading market and how they could be grouped to create a calssification system for this new investment.

The purpose of this report and classification is Accountability Accounting a prominent investment bank is interested in offering a new cryptocurrency investment portfolio for its customers , and would like to use this report and classification to better understand the current market place.

The dataset we have is not ideal , so we will need to process the data to fit a machine learning model , as there is no known output for this data set it has been decided to use unsupervised learning.

To group the cryptocurrencies we will use a clustering algorithm and use some data visualizations to share the findings.

## Overview of the analysis

There are 4 main phases on this analysis

1. Preprocessing the Data for PCA
2. Reducing Data Dimensions Using PCA
3. Clustering Cryptocurrencies Using K-means
4. Visualizing Cryptocurrencies Results

## Deliverable 1 : Preprocessing the Data for PCA

### Summary Processing

Read in the data set and use pandas to process the dataset to format and filter accordingly, to :- 

- Create a dataframe containing relevant values
- Create a dataframe containing cryptocurrency names
- Create a dataframe containing variable for the test features
- The features dataframe has been standardized using the StandardScaler function

During the preporcessng we will peform the following :- 

1.	Keep all the cryptocurrencies that are being traded.
2.	Keep all the cryptocurrencies that have a working algorithm.
3.	Drop the IsTrading column.
4.	Remove rows that have at least one null value.
5.	Filter the crypto_df DataFrame so it only has rows where coins have been mined.
6.	Create a new DataFrame that holds only the cryptocurrency names, and use the crypto_df DataFrame index as the index for this new DataFrame.
7.	Remove the CoinName column from the crypto_df DataFrame since it's not going to be used on the clustering algorithm.

### Results

The images below are sample output of the dataframes , note the dataframe a larger than displayed.

The image belows shows a sample of the dataframe after all the preprocessing steps have been completed.

![After prepocessing](/Resources/Del1_relevant_values.png)

The image belows shows a sample of the dataframe containing cryptocurrency names.

![cryptocurrency names](/Resources/Del1_coinnames.png)

The image belows shows a sample of the dataframe containing variable for the test features.

![test features](/Resources/Del1_testfeatures.png)

The image belows shows a sample of the output using the StandardScaler function.

![StandardScaler function](/Resources/Del1_standardScaler.png)


## Deliverable 2 : Reducing Data Dimensions Using PCA

### Summary Processing

- Use the PCA algorithm reduces the dimensions of the X DataFrame down to three principal components
- A DataFrame is created and has the following three columns, PC 1, PC 2, and PC 3, and has the index from the crypto_df DataFrame

### Results

The images below are sample output of the dataframes , note the dataframe a larger than displayed.

The image belows shows a sample of the dataframe after applying PCA steps have been completed.

![After pca](/Resources/Del2_dataframe.png)

## Deliverable 3 : Clustering Cryptocurrencies Using K-means

### Summary Processing

- Using the K-means algorithm cluster the cryptocurrencies using the PCA data.
- An elbow curve is created using hvPlot to find the best value for 
- Predictions are made on the K clusters of the cryptocurrencies’ data
- Create a datframe with the same index as the crypto_df DataFrame and has the following columns: Algorithm, ProofType, TotalCoinsMined, TotalCoinSupply, PC 1, PC 2, PC 3, CoinName, and Class

### Results

The image below shows the elbow curve created.

![Elbow Curve](/Resources/Del3_Elbow_Curve.png)

From the above we can determine that 4 clusters is the initial point.

The image below show the output of an analysis using K = 4 eithin the K-means alogrithm.

![K Means](/Resources/Del_3_K_means.png)

The image below shows a sample of the dataframe created.

![Cluster DF](/Resources/Del3_dataframe.png)

## Deliverable 4 : Visualizing Cryptocurrencies Results

### Summary Processing

The following vizualizations will be created in this deliverable.

- The clusters are plotted using a 3D scatter plot, and each data point shows the CoinName and Algorithm on hover
- A table with tradable cryptocurrencies is created using the hvplot.table() function
- The total number of tradable cryptocurrencies is printed
- A DataFrame is created that contains the clustered_df DataFrame index, the scaled data, and the CoinName and Class columns
- A hvplot scatter plot is created where the X-axis is "TotalCoinsMined", the Y-axis is "TotalCoinSupply", the data is ordered by "Class", and it shows the CoinName when you hover over the data point

### Results

The image below shows the 3-D-Scatter with PCA data and the clusters

![3D scatter plot](/Resources/Del4_image_1.png)

The image below shows tradable cryptocurrencies ( created using the hvplot.table() )

![Tradable](/Resources/Del4_image_2.png)

The image below shows total number of tradable cryptocurrencies 

![Total](/Resources/Del4_image_3.png)

The image below the dataFrame containing the clustered_df DataFrame index, the scaled data, and the CoinName and Class columns

![Cluster](/Resources/Del4_image_4.png)

The image below shows the 3-D-Scatter hvplot scatter plot is created where the X-axis is "TotalCoinsMined", the Y-axis is "TotalCoinSupply", the data is ordered by "Class", and it shows the CoinName when you hover over the data point

![Cluster](/Resources/Del4_image_5.png)
