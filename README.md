# 🛍️ Customer Segmentation: The Clustering Showdown (K-Means vs. DBSCAN vs. HDBSCAN)

## 📋 Project Overview
This repository implements a robust unsupervised learning pipeline to segment retail customers based on purchasing behavior. By comparing **Centroid-based (K-Means)** and **Density-based (DBSCAN/HDBSCAN)** architectures, this project demonstrates how to identify high-value customer micro-segments and navigate "noisy" real-world data using dimensionality reduction.

The project follows a **Professional Analytics Workflow**, ensuring that clusters are not just mathematically sound but also visually interpretable through PCA.

---

## 🏗️ Systematic Workflow

### 1. Data Processing & Dimensionality Reduction
* **Feature Scaling:** Implemented `StandardScaler` to normalize features like `Annual Income` and `Spending Score`. This is a mechanical necessity for distance-based algorithms like K-Means and DBSCAN.
* **Principal Component Analysis (PCA):** Since humans cannot visualize multi-dimensional data, I utilized PCA to reduce the feature space to 2 components (`PC1`, `PC2`) for 2D plotting while retaining maximum variance.
* **Missing Value Handling:** Automated dropping of null entries to ensure pipeline stability.

### 2. The Model Battle
To identify the most robust predictor, three distinct mathematical architectures were evaluated:
* **Partition-Based (K-Means):** Establishes a linear boundary between segments; optimized using the **Elbow Method** ($k=5$).
* **Density-Based (DBSCAN):** Leverages spatial proximity to identify clusters of any shape while explicitly flagging **outliers (Noise)**.
* **Hierarchical Density (HDBSCAN):** An advanced evolution of DBSCAN that handles clusters of varying densities, providing the most nuanced micro-segmentation.

---

## 📊 Performance Metrics & Visual Insights

In clustering, success is measured by **Spatial Separation** and **Density** rather than standard accuracy scores.

| Metric / Feature | K-Means | DBSCAN | HDBSCAN |
| :--- | :--- | :--- | :--- |
| **Outlier Detection** | No (Forces all points) | **Yes (Label -1)** | **Yes (Robust noise handling)** |
| **Cluster Shape** | Spherical / Fixed | Geometry-independent | Geometry-independent |
| **Best Hyperparameter**| $k=5$ | $eps=0.5$ | $min\_cluster\_size=5$ |

### Visual Analysis
![Clustering Results Comparison](your_uploaded_screenshot_name.jpg)
* **K-Means:** Provides the "cleanest" looking split, ideal for broad marketing tiers.
* **DBSCAN:** Best at identifying customers who don't fit the typical mold (Noise).
* **HDBSCAN:** Successfully isolated dense core groups while ignoring the background "scatter" of non-typical shoppers.

---

## ⚙️ Configuration & Hyperparameters
Following the **Industry Checklist**, the following parameters provided the most stable results:
* **Algorithm:** K-Means (Optimized with `k-means++` initialization).
* **DBSCAN:** Optimized with `eps=0.5` and `min_samples=5`.
* **HDBSCAN:** Configured with `min_cluster_size=5` to balance micro-segmentation.
* **Dimensionality:** PCA set to `n_components=2` for optimal visualization.

---

## 🚀 Deployment & Running Instructions

### Option 1: Google Colab (Recommended)
1. Open the `Clustering Project.ipynb` notebook in Colab.
2. Run the code cells; it will prompt you to upload the dataset.
3. Upload `Customers_Segmentation.csv`.
4. The pipeline will automatically handle cleaning, scaling, and visualization.

### Option 2: Local Environment
1. Clone the repo: `git clone https://github.com/shivisrivastava0212/customer-segmentation-clustering-comparison.git`
2. Install dependencies: `pip install pandas scikit-learn hdbscan seaborn matplotlib jupyter`
3. Ensure the `Customers_Segmentation.csv` file is in the same directory as the notebook.
4. Run: `jupyter notebook "Clustering Project.ipynb"`

---

## 🧠 Lessons Learned
* **Algorithm Sensitivity:** Observed firsthand how K-Means struggles with outliers, whereas HDBSCAN naturally ignores them to find "core" behaviors.
* **The Power of PCA:** Learned that reducing dimensions is critical—not just for visualization, but for removing "noise" before clustering.
* **Realistic Constraints:** Realized that in retail, identifying the "Noise" (unique customers) is often as valuable as identifying the "Segments."

---

## 👤 Author
**Shivi Srivastava** Aspiring AI Engineer | Amity University Uttar Pradesh  
[LinkedIn Profile](https://www.linkedin.com/in/shivi-srivastava-0b4b2b2a0/) | [GitHub Portfolio](https://github.com/shivisrivastava0212)
