# 📈 Stock Market Structural Analysis via PCA (VN30 Index)

An empirical data science project applying **Principal Component Analysis (PCA)** to decipher the underlying market structure, sectoral drivers, and systemic risk factors within the Vietnamese stock market (specifically the **VN30 Index**).

---

## 📑 Table of Contents
* [Project Overview](#-project-overview)
* [Key Objectives](#-key-objectives)
* [Methodology & Workflow](#-methodology--workflow)
* [Tech Stack](#-tech-stack)
* [Project Structure](#-project-structure)
* [Key Insights & Visualizations](#-key-insights--visualizations)
* [Installation & Usage](#-installation--usage)

---

## 🎯 Project Overview
In quantitative finance, stock movements are driven by a combination of market-wide forces (systemic risk) and asset-specific events (idiosyncratic risk). This project utilizes **unsupervised machine learning (PCA)** on the historical daily returns of the top 30 blue-chip stocks in Vietnam to isolate the latent variables driving the overall market index.

---

## 🚀 Key Objectives
* **Deconstruct Market Volatility:** Extract the dominant principal components that govern the co-movements of VN30 constituent stocks.
* **Quantify Systemic Risk:** Measure market integration by analyzing the percentage of total variance explained by the first few components.
* **Identify Market Leaders:** Evaluate factor loadings (weights) to pinpoint which specific stocks or sectors wield the most significant influence on the index factor.

---

## 🛠️ Methodology & Workflow

### 1. Data Preprocessing & Synchronization
* **Alignment:** Synchronizing historical price data to handle discrepancies caused by trading halts, illiquidity, or public holidays.
* **Stationarity:** Transforming absolute closing prices into **Daily Log-Returns** to ensure statistical stationarity before performing matrix decomposition.

### 2. Statistical Normalization
* Standardizing the return series using **Z-score normalization** (Mean = 0, Std = 1).
* Computing the Covariance Matrix on standardized data, which mathematically equates to the **Correlation Matrix**. This eliminates volatility bias, preventing high-volatility stocks from artificially dominating the components.

### 3. Principal Component Decomposition
* Applying Eigen-decomposition to extract **Eigenvalues** and **Eigenvectors**.
* Plotting a **Scree Plot** to analyze the cumulative explained variance.
* Mapping the first Principal Component ($PC1$) against the benchmark **VN30-Index** to validate its behavior as the "Market Factor".

---

## 💻 Tech Stack

| Category | Technologies |
| :--- | :--- |
| **Language** | ![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white) |
| **Data Libraries** | ![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat-square&logo=pandas&logoColor=white) ![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat-square&logo=numpy&logoColor=white) |
| **Machine Learning** | ![Scikit-Learn](https://img.shields.io/badge/scikit_learn-F7931E?style=flat-square&logo=scikit-learn&logoColor=white) |
| **Visualization** | ![Matplotlib](https://img.shields.io/badge/Matplotlib-ffffff?style=flat-square&logo=matplotlib&logoColor=black) ![Seaborn](https://img.shields.io/badge/Seaborn-4C72B0?style=flat-square) |
| **Environment** | ![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=flat-square&logo=jupyter&logoColor=white) ![Google Colab](https://img.shields.io/badge/Google_Colab-F9AB00?style=flat-square&logo=googlecolab&logoColor=white) |

---

## 📁 Project Structure
```text
├── assets/                  # Generated plots and figures
│   ├── pc1_loadings.png     # Individual stock weights on PC1
│   ├── pc1_vs_vn30.png      # Time-series comparison: PC1 vs VN30 Index
│   └── scree_plot.png       # Cumulative explained variance plot
├── notebook/                # Jupyter Notebooks containing the source code
│   └── PCA_VN30_Analysis.ipynb
├── .gitignore               # Rules for ignoring unneeded files in Git
├── README.md                # Project documentation and summary
└── requirements.txt         # List of Python dependencies
