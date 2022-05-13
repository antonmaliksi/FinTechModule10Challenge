# Crypto Portfolio Proposal
## Overview & Features
To the Board of Directors, I'm honored to present to you a prototype of my proposed Crypto Portfolio using various "unsupervised" Machine Learning methods.


This prototype utilizes the following steps:
1. Utilizing K-Means to find the best value of different cryptocurrencies.
2. Clustering the crypto values with the K-Mean data.
3. Optimizing the clusters with Principal Component Analysis
4. Finding the best value for K-means using the PCS data
5. Further clustering of PCA data
6. Final visual and comparison of data.

>![coins](https://github.com/antonmaliksi/FinTechModule10Challenge/blob/main/Readme%20Resources/coins.png)

---

## Technologies

This prototype notebook utilizes **Python (v 3.9.7)** and the following libraries:

1. pandas
2. hvplot
3. Path from pathlib
4. KMeans from sklearn.cluster
5. PCA from sklearn.decomposition
6. StandardScalar from sklearn.preprocessing

---

## Installation Guide
Pandas and Pathlib should be part of the base applications that were installed with the Python version above; if not, you will have to install them through the pip package manager of Python.

To install scikit-learn, run the following:

    ```
    pip install -U scikit-learn
    ```

To install hvPlot, run the following:

    ```
    conda install -c pyviz hvplot
    ```
    
After installing, run the following to ensure that sklearn and hvplot are installed:

    ```
    conda list scikit-learn
    
    conda list hvplot
    ```
    
If any errors occur, please contact IT for further assistance.

---

## User Guide
To use the prototype notebook in Jupyter Labs:

### Part 1: Loading the Data
1. Open "crypto_investments.ipynb"
2. Look for the following code:
    ```python
    df_market_data = pd.read_csv(
    Path("Resources/crypto_market_data.csv"),
    index_col="coin_id")
    ```
Please ensure that the .csv you wish to use is imported from the Resources folder.

### Part 2: Preparing the Data
Before analyzing the data, we need to first use the ```StandardScalar()``` module to normalize our data. We will then create a pandas DataFrame with the new scaled data.

>![prepare](https://github.com/antonmaliksi/FinTechModule10Challenge/blob/main/Readme%20Resources/prepare.PNG)

### Part 3: Find "k" value using Data
The K-means algorithm is an unsupervised learning algorithm that identifies clusters and provides many types of data for further analysis or manipulation. Using the "k" value helps us cluster segments of data together, providng a refined set of data.

To retrieve the k-value of our original data, we create a list with a range from 1 to 11; most data sets usually have their k-value between 3-6, so we set 11 as a max to account for outliers and provide a full spectrum of data.

Computing K-value                         |  Finding our K value using visualization
:----------------------------------------:|:----------------------------------------:
![prepare](https://github.com/antonmaliksi/FinTechModule10Challenge/blob/main/Readme%20Resources/kmeansOG.PNG)  | ![vizOG](https://github.com/antonmaliksi/FinTechModule10Challenge/blob/main/Readme%20Resources/vizOG.PNG)

### Part 4: Clustering Cryptocurrencies with KMeans using the Original Data
We want to visualize the clustering of our KMeans for further analysis. To accomplish this, we do the following:

Code                                         |  Crypto Scatter Plot with k-4
:-------------------------------------------:|:--------------------------------:
>![ogmodel](https://github.com/antonmaliksi/FinTechModule10Challenge/blob/main/Readme%20Resources/OGmodel.PNG)  |  >![ogscatter](https://github.com/antonmaliksi/FinTechModule10Challenge/blob/main/Readme%20Resources/OGscatter.PNG)

### Part 4: Optimize Clusters with Principal Component Analysis (PCA)
Principal Component Analysis (PCA) is a statistical technique used to accelerate machine learning algorithms when too many features exist. This is exectued to increase interpretability and minimize information loss.
1. Look for the following code:
    ```python
    crypto_pca_data = pca.fit_transform(df_market_data_scaled)
    ```
Remember that using the ```fit_transform()``` function creates an Array of the data. Running pandas syntax without first converting the Array into a DataFrame will result in a Traceback.

---

## Versioning History
All Github commits/pulls were conducted and verified by Anton Maliksi.

---

## Contributors
Anton Maliksi was the sole contributor for this Prototype.

---

## Licenses
No licenses were used for this project.