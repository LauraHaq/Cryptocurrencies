# Cryptocurrencies
## Analysis Overview
Purpose of this project is to assist a client to possibly offer a new investment option for thier customers in cryptocurrency. They have requested a report on the current crytocurrencies broken down in a classification system. However, there is no known labeled system that they are grouped by. This can be completed through Unsupervised Machine Learning algorithms after data is selected, preprocessed and transformed. The final product will be a visualization of data points of each cryptocurrency grouped by classes found through the use of KMeans.

## Resources
#### Data source: [crypto_data.csv](https://github.com/LauraHaq/Cryptocurrencies/blob/main/crypto_data.csv)
#### Tools: 
  - Jupter Notebook
  - mlenv
  - python

## Results
Above csv file loaded 1,252 rows of data as seen below using shape() function. Then after Data Selection of current cryptocurrencies that "Is Trading" the data decresed to 1,144 rows of data.  
![img](https://github.com/LauraHaq/Cryptocurrencies/blob/main/initial_dataframe2.png)

After continued data cleaning by dropping row with null values using the dropna() function and keeping rows were "TotalCoinsMined" was greater than zero the final row count to be used is 532. Then, to be able to create clusters through algorithms need get_dummies() function used on features with text as values. With this new dataframe fit_transform() function was used to standardize the size of values for ease. 
![img](https://github.com/LauraHaq/Cryptocurrencies/blob/main/initial_datafram_ready.png)

A new dataframe is created breaking up each row into three components using Principal Component Analysis (PCA) model then that was used to create Elbow Curve to find best value for K.
![img](https://github.com/LauraHaq/Cryptocurrencies/blob/main/elbow_curve.png)  
The curve shows best value of K is 4 and will be used to initiate the K-Means model.
![img](https://github.com/LauraHaq/Cryptocurrencies/blob/main/KMeans_4.png)

Then the dataframe created with PCA and the "Class" was joined to the original features to create 3D model to visualize the clusters with features when hovering.  
![img](https://github.com/LauraHaq/Cryptocurrencies/blob/main/3d_model.png)

Final is a scatter plot of TotalCoinedMined versus TotalCoinSupply.  
![img](https://github.com/LauraHaq/Cryptocurrencies/blob/main/totalcoinesmined_totalcoinsupply.png)
## Summary
Through Unsupervised Machine Learning an incomplete long data csv file was transformed into visual tools for quick understanding of current cryptocurrency to share to customers who may be interested in investing. One take away is that using the hover option on the graphs we learn that bitTorrent is the data point that looks like an outlier to the rest of the data in the graphs above. However, through a selectable table created in file it is validated that BitTorrent is in a class of its own. As it should be the highest with the amount mined it should be the highest supply. So, the one I would question is the data point that is even higher as seen on the last 2d graph but has mine just as less as the other data. This make me think this company is currently investing in purchasing a lot of coins. This information may be of use in deciding which coin to invest in. 
These graphs were successful in helping the user gain understanding such as I did with no previous knowledge and would be useful in a portfolio as a general overview. However, these tools alone are not enough to persuade the customer with beneificial data of the return you get in the investment. 
