Customer Segmentation on Brazilian E-commerce (Olist Dataset)
Overview

This project performs customer segmentation on the Brazilian Olist e-commerce dataset using RFM analysis (Recency, Frequency, Monetary) and K-Means clustering. The goal is to categorize customers into distinct groups for better marketing and business decision-making.

By understanding customer behavior, businesses can:

Identify high-value loyal customers

Detect at-risk or churn-prone customers

Tailor marketing campaigns and retention strategies

Dataset

The project uses multiple Olist datasets:

Customers: customer IDs and basic info

Orders: order timestamps and status

Order Items & Payments: product details and payment values

Products & Reviews: additional context for analysis

All datasets were merged to create a single orders_full table for customer-level analysis.

Steps / Methodology

Data Cleaning

Filtered orders to include only completed transactions (delivered or shipped)

Removed duplicate order_ids and customer_ids to avoid double counting

RFM Feature Engineering

Recency: days since last purchase (using dataset max date + 1 day as reference)

Frequency: total number of purchases per customer

Monetary: total amount spent per customer

Applied log transformation to reduce skewness and then standardized features

Clustering with K-Means

Determined optimal number of clusters using:

Elbow Method (inertia) for compactness

Silhouette Score for cluster separation

Business interpretability of clusters

Final choice: k = 4 clusters

Cluster Profiling

Calculated average RFM values per cluster

Labeled clusters for business understanding:

High-Value Loyal

New / Recent

At-Risk / Churn Risk

Occasional

Dimensionality Reduction & Visualization

Applied PCA (2 components) to visualize clusters in 2D

Plotted clusters using Plotly for interactive exploration

Key Insights

Cluster 0: At-Risk / Churn Risk → long time since last purchase, low frequency

Cluster 1: High-Value Loyal → recent purchases, frequent, high monetary value

Cluster 2: Occasional → low frequency, moderate spending

Cluster 3: New / Recent → recent buyers, low frequency

These insights can guide marketing campaigns, loyalty programs, and retention strategies.

Tools & Libraries

Python: pandas, numpy, matplotlib, seaborn, plotly

Machine Learning: scikit-learn (K-Means, StandardScaler, PCA, silhouette_score)


Conclusion

This project demonstrates end-to-end customer segmentation using real-world e-commerce data.
It combines data cleaning, feature engineering, clustering, evaluation, and visualization to generate actionable business insights.
