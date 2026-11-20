<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:CC0000,50:8B0000,100:1a1a2e&height=260&section=header&text=Mall%20Customer%20Segmentation&fontSize=48&fontColor=ffffff&animation=fadeIn&fontAlignY=36&desc=K-Means%20%C2%B7%20Agglomerative%20Hierarchical%20%C2%B7%20DBSCAN&descSize=20&descAlignY=58" width="100%" alt="Mall Customer Segmentation banner"/>

<a href="https://git.io/typing-svg"><img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=22&duration=3000&pause=800&color=CC0000&center=true&vCenter=true&width=700&lines=Unsupervised+Learning+%7C+PR+1;200+Customers+%E2%86%92+5+Behavioural+Segments;Comparing+3+Clustering+Algorithms;Turning+Data+into+Marketing+Strategy" alt="Typing SVG" /></a>

<br/>

<!-- Tech badges -->
![Python](https://img.shields.io/badge/Python-3.14-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?style=for-the-badge&logo=jupyter&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-1.9.1-F7931E?style=for-the-badge&logo=scikitlearn&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-3.0.5-150458?style=for-the-badge&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-2.5.3-013243?style=for-the-badge&logo=numpy&logoColor=white)
![Dataset](https://img.shields.io/badge/Dataset-Kaggle-20BEFF?style=flat-square&logo=kaggle&logoColor=white)
![SciPy](https://img.shields.io/badge/SciPy-1.18.1-8CAAE6?style=for-the-badge&logo=scipy&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-3.11.2-11557C?style=for-the-badge&logo=plotly&logoColor=white)
![Seaborn](https://img.shields.io/badge/Seaborn-0.13.2-4C8CBF?style=for-the-badge)


<br/>

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Rensee%20Gajipara-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/rensee-gajipara)
[![Gmail](https://img.shields.io/badge/Gmail-renseegajipara@gmail.com-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:renseegajipara@gmail.com)
[![GitHub](https://img.shields.io/badge/GitHub-RENSEE--GAJIPARA-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/RENSEE-GAJIPARA)

</div>

---

## 📑 Table of Contents

- [🎯 Project Overview](#-project-overview)
- [📊 Dataset](#-dataset)
- [🧭 Methodology](#-methodology)
- [🔍 Exploratory Data Analysis](#-exploratory-data-analysis)
- [🔴 K-Means Clustering](#-k-means-clustering)
- [🌳 Agglomerative Hierarchical Clustering](#-agglomerative-hierarchical-clustering)
- [⚫ DBSCAN](#-dbscan)
- [⚖️ Algorithm Comparison](#️-algorithm-comparison)
- [💼 Business Insights](#-business-insights)
- [🎬 Demo Video](#-demo-video)
- [📁 Repository Structure](#-repository-structure)
- [⚙️ Installation & Usage](#️-installation--usage)
- [🛠️ Tech Stack](#️-tech-stack)
- [👤 Author](#-author)

---

## 🎯 Project Overview

A mall wants to know **who its customers really are** — not by guesswork, but by behaviour. This project applies **three unsupervised learning algorithms** to the *Mall Customer Segmentation* dataset to discover natural customer groups based on **annual income** and **spending score**, then translates each group into an actionable marketing strategy.

| | |
|---|---|
| **Course** | Unsupervised Learning — Red & White Skill Education |
| **Project** | Practical Report 1 (PR 1) |
| **Algorithms** | K-Means · Agglomerative Hierarchical (Ward) · DBSCAN |
| **Goal** | Segment 200 customers and compare algorithm behaviour |
| **Key Result** | **5 customer segments**, silhouette ≈ **0.55** (K-Means & Hierarchical) |

<div align="center">

![Wave divider](https://capsule-render.vercel.app/api?type=rect&color=0:CC0000,100:1a1a2e&height=3&section=header)

</div>

## 📊 Dataset

| Field | Detail |
|---|---|
| **Name** | Mall Customer Segmentation Data |
| **Source** | [![Kaggle](https://img.shields.io/badge/Kaggle-Dataset-20BEFF?style=flat-square&logo=kaggle&logoColor=white)](https://www.kaggle.com/datasets/vjchoudhary7/customer-segmentation-tutorial-in-python) |
| **File** | `Mall_Customers.csv` — 200 rows × 5 columns |
| **Quality** | No missing values, no duplicates |
| **Domain** | Retail / Customer Analytics |
| **License** | CC0: Public Domain |

| Column | Type | Description |
|---|---|---|
| `CustomerID` | Integer | Unique identifier (1–200) — dropped before modelling |
| `Gender` | Categorical | Male / Female — label-encoded (Female = 0, Male = 1) |
| `Age` | Integer | Age in years (18–70) |
| `Annual Income (k$)` | Numeric | Annual income in thousand USD (15–137) → renamed `Annual_Income` |
| `Spending Score (1-100)` | Integer | Mall-assigned score based on purchase frequency and amount → renamed `Spending_Score` |

## 🧭 Methodology

```mermaid
flowchart LR
    A[Load CSV] --> B[Clean & Encode]
    B --> C[EDA]
    C --> D[StandardScaler]
    D --> E[2-Feature Subset<br/>Income + Spending]
    E --> F[K-Means]
    E --> G[Hierarchical]
    E --> H[DBSCAN]
    F --> I[Compare & Evaluate]
    G --> I
    H --> I
    I --> J[Business Insights]
```

1. **Preprocessing** — drop `CustomerID`, rename columns, encode `Gender`.
2. **Scaling** — `StandardScaler` on `Age`, `Annual_Income`, `Spending_Score`, so no feature dominates distance calculations because of its raw range.
3. **Feature selection** — `Annual_Income` and `Spending_Score` (`df_2f`) give clearly separable groups and allow direct 2D visualisation without PCA.
4. **Modelling** — K-Means, Agglomerative (Ward linkage), and DBSCAN.
5. **Evaluation** — Elbow method, silhouette score, dendrogram, k-distance plot, and side-by-side visual comparison.

## 🔍 Exploratory Data Analysis

### Univariate Distributions

<div align="center">
<img src="Images/01_histograms.png" alt="Histograms of Age, Annual Income and Spending Score" width="100%"/>
</div>

- **Age** is right-skewed, with most customers between 20 and 50.
- **Annual Income** is roughly bell-shaped, with a long right tail up to ~137k$.
- **Spending Score** is centred near 50, with spread at both extremes.

### Pairplot

<div align="center">
<img src="Images/02_pairplot.png" alt="Pairplot of Mall customer features" width="80%"/>
</div>

The **Annual Income vs Spending Score** panel shows five visibly distinct groups, which is why this pair was selected for clustering.

### Correlation Heatmap

<div align="center">
<img src="Images/03_correlation_heatmap.png" alt="Correlation heatmap" width="60%"/>
</div>

Correlations are weak overall. The only notable one is **Age ↔ Spending Score (−0.33)**, so younger customers tend to spend more. Income and spending are almost uncorrelated (0.01), so linear models would miss the structure that clustering reveals.

## 🔴 K-Means Clustering

### Choosing k

<div align="center">
<table>
<tr>
<td align="center"><b>Elbow Method</b><br/><img src="Images/04_elbow_method.png" alt="Elbow method" width="100%"/></td>
<td align="center"><b>Silhouette Score</b><br/><img src="Images/05_silhouette_scores.png" alt="Silhouette scores" width="100%"/></td>
</tr>
</table>
</div>

Both methods agree: **k = 5**. The inertia curve bends at k = 5, and the silhouette score peaks there at **≈ 0.55**.

### Final Clusters

<div align="center">
<img src="Images/06_kmeans_clusters.png" alt="K-Means clusters" width="75%"/>
</div>

### Segment Profiles

| Cluster | Customers | Avg Age | Avg Income (k$) | Avg Spending | Segment |
|:---:|:---:|:---:|:---:|:---:|---|
| 0 | 81 | 42.7 | 55.3 | 49.5 | 🟦 **Average Customers** — mid income, mid spending |
| 1 | 39 | 32.7 | 86.5 | 82.1 | 💎 **Premium Spenders** — high income, high spending |
| 2 | 22 | 25.3 | 25.7 | 79.4 | 🛍️ **Young Enthusiasts** — low income, high spending |
| 3 | 35 | 41.1 | 88.2 | 17.1 | 💰 **Frugal Affluent** — high income, low spending |
| 4 | 23 | 45.2 | 26.3 | 20.9 | 🪙 **Budget Conscious** — low income, low spending |

> Cluster numbering can differ between runs or library versions; the segment definitions stay the same.

## 🌳 Agglomerative Hierarchical Clustering

<div align="center">
<img src="Images/07_dendrogram.png" alt="Dendrogram with Ward linkage" width="90%"/>
</div>

**Ward linkage** merges the pair of clusters that causes the smallest increase in total within-cluster variance. Cutting the dendrogram at the longest vertical gap gives **5 clusters**.

<div align="center">
<img src="Images/08_hierarchical_clusters.png" alt="Hierarchical clusters" width="75%"/>
</div>

### K-Means vs Hierarchical

<div align="center">
<img src="Images/09_kmeans_vs_hierarchical.png" alt="K-Means vs Hierarchical comparison" width="100%"/>
</div>

The two methods produce **almost identical segments** (silhouette 0.555 vs 0.554). Differences appear only for border customers where clusters meet. K-Means assigns by distance to a centroid, while Ward builds clusters bottom-up by connectivity.

## ⚫ DBSCAN

### Estimating `eps`

<div align="center">
<img src="Images/10_k_distance_plot.png" alt="4-NN distance plot" width="70%"/>
</div>

The knee of the sorted 4-nearest-neighbour distance curve suggests **eps ≈ 0.4**.

### Final Clusters

<div align="center">
<img src="Images/11_dbscan_clusters.png" alt="DBSCAN clusters" width="75%"/>
</div>

| Parameter | Value |
|---|---|
| `eps` | 0.4 |
| `min_samples` | 5 |
| Clusters found | 4 |
| Noise points | 15 (labelled `-1`, shown as ✖) |
| Silhouette (excl. noise) | ≈ 0.48 |

DBSCAN needs no preset *k* and flags low-density customers as noise. Because the two low-income segments sit close together, it merges them into one dense region, giving 4 clusters instead of 5. The extreme high-income customers become noise.

## ⚖️ Algorithm Comparison

| Algorithm | Clusters | Silhouette | Needs k? | Handles Noise? | Strength |
|---|:---:|:---:|:---:|:---:|---|
| **K-Means** | 5 | **≈ 0.555** | ✅ Yes | ❌ No | Fast, interpretable centroids |
| **Hierarchical (Ward)** | 5 | ≈ 0.554 | ✅ Yes (cut level) | ❌ No | Dendrogram hierarchy |
| **DBSCAN** | 4 + noise | ≈ 0.48 | ❌ No | ✅ Yes | Arbitrary shapes, outlier detection |

**Verdict:** K-Means and Hierarchical clustering agree on the same five segments, and those segments are the most stable across all three algorithms. K-Means is recommended for deployment because it is simple, fast and easy to explain.

## 💼 Business Insights

| Segment | Recommended Marketing Action |
|---|---|
| 💎 **Premium Spenders** (high income, high spend) | VIP loyalty programme, early access to new collections, personalised offers |
| 🛍️ **Young Enthusiasts** (low income, high spend) | Budget promotions, student/youth discounts, trend-driven campaigns, buy-now-pay-later |
| 🟦 **Average Customers** (mid income, mid spend) | Seasonal sales, bundle deals, points-based rewards to lift spending |
| 💰 **Frugal Affluent** (high income, low spend) | Re-engagement campaigns, premium experiences, exclusive events to unlock their purchasing power |
| 🪙 **Budget Conscious** (low income, low spend) | Clearance sales, value coupons, low-cost footfall drivers |

**Algorithm recommendation:** use **K-Means** for deployment (most interpretable), **Hierarchical** for management presentations that need a hierarchy, and **DBSCAN** when cluster shapes are unknown or outlier detection matters.

## 🎬 Demo Video

<div align="center">

[![Watch the Demo](https://img.shields.io/badge/▶%20Watch%20the%20Demo%20Video-Google%20Drive-CC0000?style=for-the-badge&logo=googledrive&logoColor=white)](https://drive.google.com/file/d/1UbVq952eUp7kKtN1cpgjQ-H4GSJmF0Qw/view?usp=sharing)

</div>

A walkthrough of the complete project: dataset and EDA, choosing k for K-Means, reading the dendrogram, tuning DBSCAN, and the final business insights.

| | |
|---|---|
| **Format** | Face + screen recording |
| **Duration** | ~5–10 minutes |
| **Covers** | Preprocessing · K-Means · Hierarchical · DBSCAN · Comparison · Business insights |
| **Link** | [Open in Google Drive](https://drive.google.com/file/d/1UbVq952eUp7kKtN1cpgjQ-H4GSJmF0Qw/view?usp=sharing) |

## 📁 Repository Structure

```
📦 Unsupervised-Learning
 ┣ 📂 Dataset
 ┃ ┗ 📄 Mall_Customers.csv
 ┃ 
 ┣ 📂 Notebook
 ┃ ┗ 📓 Mall_Customer_Segmentation.ipynb
 ┃ 
 ┣ 📂 Images
 ┃ ┣ 🖼️ 01_histograms.png 
 ┃ ┣ 🖼️ 02_pairplot.png
 ┃ ┣ 🖼️ 03_correlation_heatmap.png
 ┃ ┣ 🖼️ 04_elbow_method.png
 ┃ ┣ 🖼️ 05_silhouette_scores.png
 ┃ ┣ 🖼️ 06_kmeans_clusters.png
 ┃ ┣ 🖼️ 07_dendrogram.png
 ┃ ┣ 🖼️ 08_hierarchical_clusters.png
 ┃ ┣ 🖼️ 09_kmeans_vs_hierarchical.png
 ┃ ┣ 🖼️ 10_k_distance_plot.png
 ┃ ┗ 🖼️ 11_dbscan_clusters.png
 ┃ 
 ┣ 📂 Reports
 ┃ ┣ 📕 Theory Report.pdf
 ┃ ┗ 🌐 HTML Report.html
 ┃ 
 ┣ 📄 requirements.txt
 ┃ 
 ┗ 📄 README.md
```

## ⚙️ Installation & Usage

```bash
# 1. Clone the repository
git clone https://github.com/RENSEE-GAJIPARA/<your-repo-name>.git
cd <your-repo-name>

# 2. Create and activate a virtual environment
python -m venv .venv
.venv\Scripts\activate        # Windows
# source .venv/bin/activate   # macOS / Linux

# 3. Install dependencies
pip install -r requirements.txt

# 4. Launch the notebook
jupyter notebook Notebook/Mall_Customer_Segmentation.ipynb
```

> Run **Kernel → Restart & Run All** to reproduce every figure. The exported HTML report in `Reports/` can be read without Jupyter.

## 🛠️ Tech Stack

| Library | Version | Purpose |
|---|---|---|
| ![pandas](https://img.shields.io/badge/pandas-150458?style=flat-square&logo=pandas&logoColor=white) | 3.0.5 | Data loading and manipulation |
| ![numpy](https://img.shields.io/badge/numpy-013243?style=flat-square&logo=numpy&logoColor=white) | 2.5.3 | Numerical computing |
| ![matplotlib](https://img.shields.io/badge/matplotlib-11557C?style=flat-square) | 3.11.2 | Plotting |
| ![seaborn](https://img.shields.io/badge/seaborn-4C8CBF?style=flat-square) | 0.13.2 | Statistical visualisation |
| ![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikitlearn&logoColor=white) | 1.9.1 | K-Means, Agglomerative, DBSCAN, metrics |
| ![scipy](https://img.shields.io/badge/scipy-8CAAE6?style=flat-square&logo=scipy&logoColor=white) | 1.18.1 | Linkage and dendrogram |

## 👤 Author

<div align="center">

**RENSEE GAJIPARA**
B.Tech — Artificial Intelligence & Data Science, Surat

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/rensee-gajipara)
[![Gmail](https://img.shields.io/badge/Gmail-Contact-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:renseegajipara@gmail.com)
[![GitHub](https://img.shields.io/badge/GitHub-Follow-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/RENSEE-GAJIPARA)

⭐ If you found this project useful, consider giving it a star!

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:1a1a2e,50:8B0000,100:CC0000&height=140&section=footer" width="100%" alt="footer wave"/>

</div>
