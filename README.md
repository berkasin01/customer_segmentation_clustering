# Customer Segmentation Clustering

Customer segmentation using K-Means clustering on retail transaction data with PCA visualisation.

## What It Does

Takes a retail sales dataset and groups customers into segments based on their purchasing behaviour. Uses K-Means clustering to find natural groupings, the elbow method to pick the right number of clusters, and PCA to visualise the results in 2D.

## Process

1. Selected features: Gender, Age, Quantity, Price per Unit, Total Amount, Product Category
2. Encoded categoricals (LabelEncoder for Gender, OneHotEncoder for Product Category)
3. Scaled all features with StandardScaler (important because K-Means uses distance)
4. Ran elbow method for K=1 to K=10 to find optimal cluster count
5. Picked K=5 based on elbow curve
6. Ran K-Means and visualised clusters using PCA (2 components)

## Customer Segments Found

| Cluster | Profile | Avg Spend | Product Focus |
|---------|---------|-----------|---------------|
| 0 | Mid-price clothing shoppers | £219 | Clothing |
| 1 | Budget beauty buyers | £99 | Beauty |
| 2 | High-value mixed shoppers | £1,436 | Clothing/Electronics |
| 3 | Mid-price electronics buyers | £209 | Electronics |
| 4 | Premium beauty buyers | £1,118 | Beauty |

Clusters split mainly by product category and spending level. The two highest-spending segments (2 and 4) buy at significantly higher price points and quantities.

## Key Findings

- Scaling data before running K-Means changed the elbow shape significantly, showing why preprocessing matters for distance-based algorithms
- PCA visualisation shows 5 clearly separated groups confirming the clusters are well-defined
- Product category is the strongest differentiator between segments
- Age and gender show minimal variation across clusters meaning they are not strong drivers of purchasing behaviour in this dataset

## Requirements
```
pip install pandas numpy matplotlib scikit-learn
```
