
# 📊 Customer Segmentation using RFM Analysis and KMeans Clustering

This project performs customer segmentation using **RFM (Recency, Frequency, Monetary)** analysis combined with **KMeans clustering**. It is built in Python with detailed preprocessing, EDA, and machine learning workflows for unsupervised segmentation.

---

## 🧠 Objectives

- Understand customer purchasing behavior using RFM metrics.
- Segment customers into distinct groups using KMeans clustering.
- Visualize and interpret customer segments for actionable insights.

---

## 📁 Dataset

The dataset used is a transactional retail dataset with fields such as:
- `InvoiceNo`, `CustomerID`, `InvoiceDate`, `Quantity`, `UnitPrice`, and `Country`.

Make sure to place the file as `data.csv` in the working directory. Encoding: `cp1252`.

---

## ⚙️ Pipeline Overview

### 1. Data Preprocessing
- Remove duplicates and handle missing values.
- Fix invalid data types (e.g., `InvoiceDate` to datetime).
- Create `TotalPrice = Quantity * UnitPrice`.
- Filter out invalid records (e.g., negative quantities or prices).

### 2. Feature Engineering: RFM Analysis
- **Recency**: Days since last purchase per customer.
- **Frequency**: Total number of unique purchases.
- **Monetary**: Total revenue per customer.

### 3. Transformation & Scaling
- Apply `log1p` transformation to reduce skewness.
- Normalize features using `StandardScaler`.

### 4. KMeans Clustering
- Use the **elbow method** to choose optimal `k`.
- Fit KMeans and assign cluster labels.
- Append cluster labels back to the RFM table.

### 5. Evaluation & Visualization
- Analyze RFM stats by cluster.
- Visualize segments using 2D PCA projection.
- Visualize recency/frequency/monetary distributions across clusters.

---

## 📊 Visualizations

- Elbow plot for WCSS vs `k`
- PCA scatter plots colored by cluster
- Box plots of R/F/M values across segments

---

## 🛠️ Requirements

```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

---

## 📌 Use Cases

- **Marketing Campaigns**: Identify top spenders, loyal customers, and at-risk customers.
- **Business Strategy**: Design personalized retention or acquisition strategies.
- **LTV Modeling**: Cluster-specific analysis for lifetime value estimation.

---

## 📈 Sample Output

| Cluster | Avg Recency | Avg Frequency | Avg Monetary | Description |
|---------|-------------|----------------|----------------|-------------|
| 0       | Low         | High           | High           | Loyal, High-Value Customers |
| 1       | High        | Low            | Low            | Inactive, Low-Value |
| 2       | Medium      | Medium         | Medium         | Potential or New |
| 3       | Low         | Low            | High           | Recent High-Spenders |

---

## 🧠 Future Work

- Try other clustering algorithms like **DBSCAN** or **Agglomerative Clustering**.
- Build a dashboard with **Plotly Dash** or **Streamlit**.
- Integrate RFM scoring (1–5 bins) for interpretable scoring system.

---
