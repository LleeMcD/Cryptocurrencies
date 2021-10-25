# Cryptocurrencies
## Module 18 Challenge Overview
### Deliverables
The deliverables were as follows:
- Deliverable 1: Preprocessing the Data for PCA
  - The following five preprocessing steps were performed on the crypto_df DataFrame:
    - All cryptocurrencies that were not being traded were removed 
    - The IsTrading column was dropped 
    - All the rows that had at least one null value were removed
    - All the rows that did not have coins being mined were removed
    - The CoinName column was dropped 
    - A new DataFrame was created to store all cryptocurrency names from the CoinName column; it retains the index from the crypto_df DataFrame
    - The get_dummies() method was used to create variables for the text features, which were then stored in a new DataFrame
    - The features from the X DataFrame were standardized using the StandardScaler fit_transform() function 
 - Deliverable 2: Reducing Data Dimensions Using PCA
    -  Principal component analysis (PCA) was used to reduce the dimensions to three principal components, which were then placed in a new DataFrame.
      - The DataFrame included the following columns, PC 1, PC 2, and PC 3, and used the index of the crypto_df DataFrame as the index.
 - Deliverable 3: Clustering Cryptocurrencies Using K-means
    - The K-means algorithm was used to cluster the cryptocurrencies using the PCA data, where the following steps had been completed:
    - An elbow curve is created using hvPlot to find the best value for K 
    - Predictions were made on the K clusters of the cryptocurrencies’ data 
    - A new DataFrame was created with the same index as the crypto_df DataFrame and has the following columns: Algorithm, ProofType, TotalCoinsMined, TotalCoinSupply, PC 1, PC 2, PC 3, CoinName, and Class
- Deliverable 4: Visualizing Cryptocurrencies Results
  - A 3D scatter plot was created using the Plotly Express scatter_3d() function to plot the three clusters from the clustered_df DataFrame.
    - The CoinName and Algorithm columns were added to the hover_name and hover_data parameters, respectively, so each data point displays the CoinName and Algorithm on hover.
   - A table with tradable cryptocurrencies was creatred using the hvplot.table() function.
   - The MinMaxScaler().fit_transform method was used to scale the TotalCoinSupply and TotalCoinsMined columns between the given range of zero and one.
    - A new DataFrame was created from the scaled data. CoinName and Class clomns were then added to the DataFrame as instructed.
    - An hvplot scatter plot with x="TotalCoinsMined", y="TotalCoinSupply", and by="Class". The CoinName is displayed when the cursor is hovered over the the data point.
