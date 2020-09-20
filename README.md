# Cryptocurrencies

## Overview
Use unsupervised machine learning models (PCA and KMeans) to find pattern in cryptocurrencies. 

## Resources
*Data*
- The [data used](https://github.com/jjin92/Cryptocurrencies/blob/master/challenge/Resources/crypto_data.csv) is retrieved from [cryptocompare](https://min-api.cryptocompare.com/data/all/coinlist)

*Software*
- Python (Jupyter Notebook)
- pandas
- sklearn
    - preprocessing/StandardScaler
    - decomposition/PCA
    - cluster/KMeans
- hvplot.pandas
- plotly.express

## Process
*1. Data preprocessing*
- Load in the data (set the first column as index) in to a dataframe and keep only the currencies under trading
- Drop the NaN and Null values
- Convert string numbers into numeric value
- Create dummies for text columns and save all features into a new dataframe `X`
- Standardize the features in `X`

*2. PCA*
- Initiate the model. Reduce features to three components.
- Fit the scaled data into the model
- Transform the PCA data to a dataframe, matching the original index

*3. KMeans*
- Create an Elbow Curve to determine K-value. We will pick K=5.

![elbow_curve](https://github.com/jjin92/Cryptocurrencies/blob/master/challenge/img/elbow_curve.png)
- Create KMeans model with 5 clusters, and generate class predictions
- Aggregate all information, PCA features, and predicted class into one dataframe

![clustered_Df](https://github.com/jjin92/Cryptocurrencies/blob/master/challenge/img/cluster_df.PNG)

*4. Visualization*
- Visualize the 3 PCA features in 3D.

![PCA_3D](https://github.com/jjin92/Cryptocurrencies/blob/master/challenge/img/PCA_3D.png)