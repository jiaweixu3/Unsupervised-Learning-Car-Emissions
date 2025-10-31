# 🚗 Unsupervised Learning: Car Fuel Emissions Analysis

A comprehensive **unsupervised learning project** in R analyzing over a decade of car fuel emissions data.  
This project demonstrates a complete **data science pipeline** — from data engineering and dimensionality reduction to advanced clustering — revealing hidden vehicle patterns related to **environmental impact, engine efficiency, and modernization**.  

The analysis combines **statistical rigor and practical interpretability**, with all findings and methodologies documented in a detailed **5-page analytical report (`REPORT.pdf`)**.

---

### 🧠 Core Competencies & Technologies

This project showcases proficiency in **statistical modeling, data cleaning, and unsupervised learning** using R.  
It highlights the ability to handle complex, high-dimensional datasets, validate model performance, and communicate insights visually and analytically.

* **Languages & Tools:** R, R Markdown  
* **Key Packages:** `mice` (Imputation) · `factoextra` (Visualization) · `mclust` (GMM) · `cluster` (Clustering) · `ggplot2`  
* **Techniques:**
  * Data Preprocessing, Imputation (MICE), and Feature Engineering  
  * Dimensionality Reduction (PCA & Factor Analysis)  
  * Clustering Algorithms (K-Means, PAM, GMM, Agglomerative & Divisive Hierarchical)  
  * Model Validation (WSS, Silhouette, Gap Statistic, BIC, ICL)

---

### 🔍 Analytical Workflow

#### 1️⃣ Data Cleaning & Preparation
- **Feature Engineering:** Removed irrelevant variables (identifiers, imperial metrics) and merged correlated ones (`fuel_cost_12000_miles` + `fuel_cost_6000_miles` → `fuel_cost`).  
- **Imputation:** Addressed missing values with **multiple imputation (`mice`)**.  
- **Outlier Detection:** Applied the **3-sigma rule**, retaining only meaningful extreme values.  
- **Standardization:** Transformed categorical variables into factors and scaled numerical features.

#### 2️⃣ Exploratory Analysis & Visualization
- Built correlation heatmaps to detect **multicollinearity** among fuel efficiency metrics.  
- Analyzed `CO` and `NOx` emissions by *Euro Standard*, illustrating how regulation drives environmental performance.

#### 3️⃣ Dimensionality Reduction
- **PCA (Principal Component Analysis):**  
  - Three components explained **76.4%** of variance.  
  - **PC1:** *Environmental Friendliness* · **PC2:** *Modernity* · **PC3:** *Engine Efficiency*  
- **FA (Factor Analysis):**  
  - Extracted 3 latent factors explaining **69%** of variance.  
  - Factors identified as:  
    1. *Environmental Impact* (CO₂, engine capacity, fuel cost)  
    2. *Fuel Price Evolution* (year, fuel type)  
    3. *Chemical Emissions* (NOx, CO)

#### 4️⃣ Clustering & Segmentation
- **K-Means & PAM:**  
  - Optimal **k = 4** via WSS, Silhouette, and Gap Statistic.  
  - Segmented vehicles into 4 tiers — *Affordable*, *Mid-Range*, *Luxury*, *Specialized*.  
- **Gaussian Mixture Models (Mclust):**  
  - Best configuration: `VEV` (ellipsoidal, equal shape) with **9 components**.  
  - Strong **BIC (-18669.28)** and **ICL (-19398.36)** confirm model validity.  
- **Hierarchical Clustering:**  
  - Used **Ward’s linkage** and **Euclidean distance** on first 5 PCA components (91.4% variance).  
  - Combined **Agglomerative (`hclust`)** and **Divisive (`diana`)** to ensure cluster consistency.

---

### 📁 Repository Contents

| File | Description |
|------|--------------|
| **UL.Rmd** | Full R Markdown analysis (preprocessing, dimensionality reduction, clustering). |
| **REPORT.pdf** | 5-page analytical report summarizing results, methods, and visual outputs. |
| **car.csv** | [Car Fuel and Emissions 2000–2013 (Kaggle)](https://www.kaggle.com/datasets/mohameds10960/car-fuel-and-emissions-2000-2013/data) — Public dataset used for modeling. |

---

### 👥 Authors
- **Iván López Anca**  
- **Jiawei Xu**
