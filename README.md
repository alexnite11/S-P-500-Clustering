# S&P 500 Company Clustering Analysis  
**Author:** Alex Nite  
**Project Type:** Unsupervised Learning (K‑Means & Hierarchical Clustering)

---

##  Project Overview
This project applies unsupervised learning techniques to explore whether companies in the S&P 500 naturally form meaningful groups based on their financial and operational characteristics. Using K‑Means and Agglomerative Hierarchical Clustering—both before and after PCA—the analysis investigates how company size, profitability, pricing, staffing, and growth patterns shape the underlying structure of the market.

The goal is not prediction, but **discovery**: allowing the data to reveal its own patterns and segmentations without predefined labels.

---

##  Features Used
Five core financial variables were selected and transformed to reduce skew and ensure fair clustering:

- **Log Market Cap** — company size  
- **Signed Log EBITDA** — profitability (handles negative values)  
- **Log Current Price** — stock price magnitude  
- **Log Full‑Time Employees** — operational scale  
- **Revenue Growth** — expansion rate  

These features capture broad economic profiles such as large‑stable firms, high‑growth niche companies, and mid‑tier performers.

---

##  Data Preparation
- Log transformations applied to skewed variables  
- Signed log transformation for EBITDA  
- Median imputation for missing values  
- Removed redundant or highly correlated features (e.g., Weight)  
- Standardized all numeric features  
- PCA applied to reduce dimensionality (90% variance → 4 components)

---

##  Principal Component Analysis (PCA)
PCA revealed four interpretable components:

- **PC1:** Company size (dominated by Market Cap)  
- **PC2:** Growth vs. staffing efficiency  
- **PC3:** Profitability relative to share price  
- **PC4:** Mixed pattern of EBITDA, price, and growth  

PCA improved cluster stability and highlighted the dominant financial dimensions.

---

## Clustering Methods

### **1. K‑Means Clustering**
Performed **pre‑PCA** and **post‑PCA**:

- **Pre‑PCA (K=4):**  
  - Average Performers  
  - Solid Mid‑Sized Growth  
  - High‑Value Giants  
  - High‑Growth Niche  

- **Post‑PCA (K=4):**  
  - Established Players  
  - Diverse Mid‑Tier  
  - High‑Cap Outliers  
  - High‑Growth Niche  

- **Post‑PCA (K=3):**  
  - Average Performers  
  - Established Players  
  - High‑Growth Niche  

K=3 produced the most balanced and interpretable segmentation.

---

## 🌳 Agglomerative Hierarchical Clustering
Hierarchical clustering (Ward’s method) was also run **pre‑ and post‑PCA**:

- **Pre‑PCA (K=4):**  
  - Outlier Extremes  
  - General S&P 500 Core  
  - Established Leaders  
  - Specialized High‑Growth Firms  

- **Post‑PCA (K=2):**  
  - Large high‑value firms  
  - Broad market core  

PCA simplified the structure but reduced nuance.

---

## Key Findings
- S&P 500 companies naturally cluster into **size‑driven** and **growth‑driven** groups  
- PCA sharpens distinctions between high‑growth and high‑value firms  
- K‑Means (K=3) provides the clearest, most actionable segmentation  
- Certain sectors (e.g., Healthcare, Industrials, Financial Services) consistently cluster together  
- High‑growth niches (often Tech/Finance) form distinct, stable clusters across methods  

---

##  Limitations
- Outliers heavily influence clustering  
- PCA reduces interpretability of transformed features  
- Sector/industry labels were not used as features, only for profiling  
- Clustering results depend on scaling and transformation choices  

---

##  Future Work
- Add additional financial ratios (ROE, ROA, debt metrics)  
- Incorporate text‑based company descriptions using NLP  
- Explore Gaussian Mixture Models for soft clustering  
- Build interactive dashboards for cluster exploration  

---

