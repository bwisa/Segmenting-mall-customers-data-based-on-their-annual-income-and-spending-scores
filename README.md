## Overview
This repository presents an end-to-end unsupervised machine learning project focused on customer segmentation for a retail shopping mall. Using demographic and behavioral features—specifically **Annual Income** and **Spending Score**—the project applies and compares two fundamental clustering techniques: **K-Means Clustering** and **Agglomerative Hierarchical Clustering**.

The primary objective is to group mall customers into distinct, actionable segments to enable targeted marketing strategies, personalized customer engagement, and optimized resource allocation.

---

## Key Features & Workflow
1. **Data Preprocessing & Scaling:** Standardized feature distributions using `MinMaxScaler` to ensure equal distance weighting during cluster distance calculations.
2. **K-Means Optimization:**
   - Applied the **Elbow Method** using Within-Cluster Sum of Squares (WCSS/Inertia) across $K \in [1, 10]$.
   - Evaluated cluster cohesion and separation using **Silhouette Analysis** and the **Davies-Bouldin Index (DBI)**.
3. **Hierarchical Clustering:**
   - Constructed and analyzed **Dendrograms** using Ward's minimum variance linkage to determine natural hierarchical splits.
   - Built and evaluated `AgglomerativeClustering` models for structural alignment.
4. **Cluster Interpretation & Visualizations:**
   - Generated scatter plots, centroid mappings, and cluster distribution bar charts.
   - Derived statistical mean profiles for each identified cluster segment (e.g., High Income / High Spenders vs. Low Income / High Spenders).

---

## Technical Stack
* **Language:** Python 3.13+
* **Data Processing:** Pandas, NumPy
* **Machine Learning:** Scikit-Learn (`KMeans`, `AgglomerativeClustering`, `silhouette_score`, `davies_bouldin_score`, `MinMaxScaler`)
* **Data Visualization:** Matplotlib, Seaborn

---

## Key Results & Insights
* **Optimal Clusters ($K$):** Identified $K = 5$ as the optimal number of clusters across both Elbow method inflection points and Silhouette score maximization (~0.555).
* **Segment Profiles:**
  - **Cluster 0:** Middle-income, average-spending core customers (largest volume segment).
  - **Cluster 1:** Low-income, high-spending shoppers (carefree/target group for impulse promotions).
  - **Cluster 2:** High-income, low-spending shoppers (careful/value-oriented target group for luxury retention).
  - **Cluster 3:** High-income, high-spending shoppers (primary target group for premium loyalty programs).
  - **Cluster 4:** Low-income, low-spending shoppers (budget-conscious segment).
