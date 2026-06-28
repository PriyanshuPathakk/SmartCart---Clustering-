<p align="center">
  <h1 align="center">🛒 SmartCart — Customer Segmentation & RFM Analytics Engine</h1>
  <p align="center">
    <em>Transforming raw customer data into actionable business personas using unsupervised ML and RFM analytics</em>
  </p>
</p>

<p align="center">
  <a href="https://www.python.org/"><img src="https://img.shields.io/badge/Python-3.10+-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python"></a>
  <a href="https://pandas.pydata.org/"><img src="https://img.shields.io/badge/Pandas-2.0+-150458?style=for-the-badge&logo=pandas&logoColor=white" alt="Pandas"></a>
  <a href="https://scikit-learn.org/"><img src="https://img.shields.io/badge/Scikit--Learn-1.3+-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white" alt="scikit-learn"></a>
  <a href="https://seaborn.pydata.org/"><img src="https://img.shields.io/badge/Seaborn-0.12+-4C72B0?style=for-the-badge&logo=python&logoColor=white" alt="Seaborn"></a>
  <a href="https://matplotlib.org/"><img src="https://img.shields.io/badge/Matplotlib-3.7+-11557C?style=for-the-badge&logo=python&logoColor=white" alt="Matplotlib"></a>
  <a href="https://jupyter.org/"><img src="https://img.shields.io/badge/Jupyter-Lab_4.0-F37626?style=for-the-badge&logo=jupyter&logoColor=white" alt="Jupyter"></a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Customers-2,240-blue?style=flat-square" alt="Customers">
  <img src="https://img.shields.io/badge/Features-22-green?style=flat-square" alt="Features">
  <img src="https://img.shields.io/badge/Personas-4-orange?style=flat-square" alt="Personas">
  <img src="https://img.shields.io/badge/Visualizations-12+-red?style=flat-square" alt="Visualizations">
  <img src="https://img.shields.io/badge/License-MIT-brightgreen?style=flat-square" alt="License">
</p>

---

## 📋 Table of Contents

- [🎯 Project Overview](#-project-overview)
- [🔬 Methodology](#-methodology)
- [📊 Key Results](#-key-results)
- [🧠 Customer Personas](#-customer-personas)
- [🛠️ Tech Stack](#️-tech-stack)
- [📁 Project Structure](#-project-structure)
- [🚀 Quick Start](#-quick-start)
- [📈 Sample Visualizations](#-sample-visualizations)
- [📝 Resume Highlights](#-resume-highlights)
- [📄 License](#-license)

---

## 🎯 Project Overview

**SmartCart** is an end-to-end customer segmentation engine that analyzes **2,240 customers** across **22 behavioral and demographic features** to uncover distinct purchasing personas. By combining **RFM (Recency-Frequency-Monetary) analysis** with **unsupervised machine learning**, the project identifies **4 actionable customer segments** with a **3.2× spending differential** between the highest and lowest value groups.

### The Business Problem

> *"How do we move from treating all customers the same to understanding and targeting distinct behavioral segments?"*

This project answers that question by building a reproducible analytics pipeline that transforms raw transactional data into **data-driven marketing strategies** with estimated revenue impact.

### What Makes This Project Stand Out

- 🔢 **Rigorous RFM scoring** with quintile-based segmentation
- 🧪 **Multi-algorithm comparison** (K-Means vs. Agglomerative vs. DBSCAN) with 3 evaluation metrics
- 📉 **Dimensionality reduction** via PCA (22 → 3 components) and t-SNE for visualization
- 🎨 **12+ publication-quality visualizations** including 3D scatter plots, radar charts, and heatmaps
- 💡 **Actionable business recommendations** per segment with revenue impact estimates

---

## 🔬 Methodology

The project follows a structured 8-stage analytics pipeline:

```
┌──────────────┐     ┌──────────────┐     ┌──────────────┐     ┌──────────────────┐
│  📥 Data     │────▶│  🔍 EDA &    │────▶│  📊 RFM      │────▶│  🔧 Feature      │
│  Ingestion   │     │  Cleaning    │     │  Analysis    │     │  Engineering     │
└──────────────┘     └──────────────┘     └──────────────┘     └──────────────────┘
                                                                        │
                                                                        ▼
┌──────────────┐     ┌──────────────┐     ┌──────────────┐     ┌──────────────────┐
│  💡 Business │◀────│  👤 Persona  │◀────│  🤖 Multi-   │◀────│  📉 PCA &        │
│  Insights    │     │  Profiling   │     │  Algorithm   │     │  Dimensionality  │
└──────────────┘     └──────────────┘     │  Clustering  │     │  Reduction       │
                                          └──────────────┘     └──────────────────┘
```

| Stage | Description |
|:------|:------------|
| **Data Ingestion** | Load and validate 2,240 records × 22 features from `smartcart_customers.csv` |
| **EDA & Cleaning** | Handle missing values, detect outliers, analyze distributions |
| **RFM Analysis** | Compute Recency, Frequency, Monetary scores using quintile binning |
| **Feature Engineering** | Create 8+ derived features: `Age`, `Tenure`, `Total_Spending`, `Total_Purchases`, `Avg_Order_Value`, `Total_Children`, composite RFM scores |
| **Dimensionality Reduction** | PCA reduces 22 features → 3 principal components (~45% variance explained) |
| **Multi-Algorithm Clustering** | Compare K-Means, Agglomerative, and DBSCAN with optimal-k selection via Elbow + Silhouette |
| **Persona Profiling** | Characterize each cluster with demographic, behavioral, and spending traits |
| **Business Insights** | Translate clusters into marketing strategies with revenue impact estimates |

---

## 📊 Key Results

### 🏆 Headline Finding

> **3.2× spending differential** between the highest-value segment (High-Value Loyalists, ~₹1,236 avg) and the lowest-value segment (At-Risk Singles, ~₹166 avg)

### Algorithm Comparison

| Algorithm | Silhouette Score | Calinski-Harabasz Index | Davies-Bouldin Index | Clusters |
|:----------|:----------------:|:-----------------------:|:--------------------:|:--------:|
| **K-Means** | ✅ Best | ✅ Best | ✅ Best | 4 |
| Agglomerative | Good | Good | Good | 4 |
| DBSCAN | Low | Low | High | Variable |

> **K-Means with k=4** emerged as the optimal configuration across all three evaluation metrics.

### Key Metrics at a Glance

| Metric | Value |
|:-------|:------|
| Dataset Size | 2,240 customers × 22 features |
| Engineered Features | 8+ new features |
| PCA Components | 3 (capturing ~45% variance) |
| Optimal Clusters | 4 |
| Spending Differential | 3.2× between top & bottom segments |
| Campaign Response Range | 3% – 32% across segments |
| Visualizations Produced | 12+ publication-quality plots |

---

## 🧠 Customer Personas

<table>
<thead>
<tr>
<th>Cluster</th>
<th>Persona</th>
<th>Key Traits</th>
<th>Avg Spend</th>
<th>Recommended Strategy</th>
</tr>
</thead>
<tbody>
<tr>
<td align="center"><b>0</b></td>
<td>🏠 <b>Budget-Conscious Families</b></td>
<td>Medium income, low spending, high number of children</td>
<td>Low–Medium</td>
<td>Family-oriented bundles, value packs, loyalty discounts on essentials</td>
</tr>
<tr>
<td align="center"><b>1</b></td>
<td>💎 <b>High-Value Loyalists</b></td>
<td>High income, catalog & in-store buyers, strong brand loyalty</td>
<td>~₹1,236</td>
<td>VIP programs, exclusive early access, premium product launches</td>
</tr>
<tr>
<td align="center"><b>2</b></td>
<td>⚠️ <b>At-Risk Singles</b></td>
<td>Low income, high web visits but low conversion, minimal engagement</td>
<td>~₹166</td>
<td>Re-engagement campaigns, personalized discounts, friction reduction in checkout</td>
</tr>
<tr>
<td align="center"><b>3</b></td>
<td>🌟 <b>Premium Solo Spenders</b></td>
<td>High income, single/no children, 32% campaign response rate</td>
<td>~₹1,190</td>
<td>Premium product curation, experiential marketing, high-AOV cross-sells</td>
</tr>
</tbody>
</table>

### Segment Distribution Insights

- **High-Value Loyalists** and **Premium Solo Spenders** together represent the top revenue-driving segments with average spends exceeding ₹1,190
- **At-Risk Singles** show high digital engagement (web visits) but poor conversion — a prime target for UX optimization
- **Budget-Conscious Families** respond well to value-driven offers and family bundle promotions
- Campaign response rates range from **~3% (At-Risk Singles)** to **~32% (Premium Solo Spenders)**, highlighting the need for differentiated marketing

---

## 🛠️ Tech Stack

| Category | Technology | Purpose |
|:---------|:-----------|:--------|
| 🐍 **Language** | Python 3.10+ | Core programming language |
| 🗂️ **Data Manipulation** | Pandas, NumPy | Data wrangling, feature engineering |
| 📊 **Visualization** | Matplotlib, Seaborn | EDA plots, heatmaps, radar charts |
| 🤖 **Machine Learning** | Scikit-learn | PCA, t-SNE, K-Means, Agglomerative, DBSCAN |
| 📐 **Optimal-k Selection** | Kneed | Elbow method for automatic knee detection |
| 📓 **Environment** | JupyterLab | Interactive notebook development |

---

## 📁 Project Structure

```
SmartCart/
│
├── 📓 smartcart.ipynb            # Main analysis notebook (end-to-end pipeline)
├── 📊 smartcart_customers.csv    # Dataset: 2,240 customers × 22 features
├── 📄 README.md                  # Project documentation (you are here)
├── 📋 requirements.txt           # Python dependencies
│
└── 📸 Visualizations (generated by notebook)
    ├── correlation_heatmap.png
    ├── pca_3d_clusters.png
    ├── tsne_2d_visualization.png
    ├── radar_chart_personas.png
    ├── elbow_curve.png
    ├── silhouette_analysis.png
    └── ... (12+ total)
```

---

## 🚀 Quick Start

### Prerequisites

- Python 3.10 or higher
- pip package manager

### Installation

```bash
# 1. Clone the repository
git clone https://github.com/<your-username>/SmartCart.git
cd SmartCart

# 2. Create a virtual environment (recommended)
python -m venv venv
source venv/bin/activate        # Linux/macOS
venv\Scripts\activate           # Windows

# 3. Install dependencies
pip install -r requirements.txt
```

### Run the Analysis

```bash
# Launch JupyterLab
jupyter lab

# Open smartcart.ipynb and run all cells (Cell → Run All)
```

> **💡 Tip:** The notebook is designed to run sequentially from top to bottom. All visualizations will be generated and saved automatically.

---

## 📈 Sample Visualizations

The notebook generates **12+ publication-quality visualizations**, including:

| Visualization | Description |
|:-------------|:------------|
| 📊 Correlation Heatmap | Feature correlation matrix across all 22+ variables |
| 🌐 3D PCA Scatter Plot | Cluster separation in 3-component PCA space |
| 🗺️ t-SNE 2D Projection | Non-linear embedding revealing cluster structure |
| 🕸️ Radar Charts | Multi-dimensional persona profiling per cluster |
| 📉 Elbow Curve | Optimal-k selection with inertia plot |
| 📏 Silhouette Analysis | Per-cluster cohesion and separation scores |
| 📦 Box Plots | Spending and income distributions by segment |
| 🔥 Cluster Heatmap | Feature intensity comparison across personas |

> All visualizations are saved as high-resolution `.png` files in the project directory when the notebook is executed.

---

## 🤝 Contributing

Contributions are welcome! Feel free to:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

---

## 📄 License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.

---

<p align="center">
  <b>Built with ❤️ for data-driven marketing</b><br>
  <sub>If you found this project useful, consider giving it a ⭐</sub>
</p>
