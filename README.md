# 🛒 E-Commerce Customer Segmentation & Product Recommendation

![Python](https://img.shields.io/badge/Python-3.10+-blue?logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-2.0+-lightgrey?logo=pandas)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-1.3+-orange?logo=scikit-learn&logoColor=white)
![Seaborn](https://img.shields.io/badge/Seaborn-0.12+-teal)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen)
![License](https://img.shields.io/badge/License-MIT-yellow)

> UK retail customer segmentation using RFM analysis & K-Means clustering, with a cosine similarity-based product recommendation system.

---

## 📌 Table of Contents

- [Overview](#-overview)
- [Dataset](#-dataset)
- [Project Pipeline](#-project-pipeline)
- [Installation](#-installation)
- [Usage](#-usage)
- [Project Structure](#-project-structure)
- [Tech Stack](#-tech-stack)

---

## 🔍 Overview

This project analyzes a real-world **UK-based online retail dataset** to understand customer behavior and drive personalized marketing decisions.

**Goals:**
- Clean and explore transactional e-commerce data
- Build an **RFM model** to score and rank customers
- Segment customers using **K-Means Clustering**
- Build a **Product Recommendation System** using Cosine Similarity

---

## 📂 Dataset

**Source:** [UCI Machine Learning Repository — Online Retail Dataset](https://archive.ics.uci.edu/ml/datasets/Online+Retail)

| Column | Description |
|--------|-------------|
| `InvoiceNo` | Unique invoice ID — prefix `C` means cancelled |
| `StockCode` | Product code |
| `Description` | Product name |
| `Quantity` | Units purchased |
| `InvoiceDate` | Date & time of transaction |
| `UnitPrice` | Price per unit (GBP £) |
| `CustomerID` | Unique customer identifier |
| `Country` | Customer's country |

> ⚠️ Dataset is not included in this repo. Download it from the UCI link above and place it as `data.csv` in the root directory.

---

## 🗺️ Project Pipeline

```
Raw Data
   │
   ├── 1. Exploratory Data Analysis (EDA)
   │       └── Missing values, duplicates, outliers, distributions
   │
   ├── 2. Data Cleaning
   │       └── Drop nulls, remove cancellations, clip outliers
   │
   ├── 3. RFM Feature Engineering
   │       └── Recency / Frequency / Monetary scoring (1–5)
   │
   ├── 4. Customer Segmentation
   │       └── K-Means + Elbow Method + Silhouette Score
   │       └── Segments: VIP / Loyal / Regular / Lost
   │
   └── 5. Product Recommendation
           ├── Item-based: Cosine Similarity
           └── Segment-based: Top products per customer tier
```

---

## 📊 Results & Visualizations

### Customer Segments

| Segment | Recency (avg) | Frequency (avg) | Monetary (avg) | Count |
|---------|--------------|-----------------|----------------|-------|
| 🏆 VIP | Low | High | High | ~10% |
| 💙 Loyal | Medium | Medium-High | Medium-High | ~25% |
| 🟡 Regular | Medium | Medium | Medium | ~40% |
| ❌ Lost | High | Low | Low | ~25% |

### Clustering Performance

| Metric | Value |
|--------|-------|
| Algorithm | K-Means (K=4) |
| Silhouette Score | **0.383** ✅ Acceptable |
| Feature Scaling | StandardScaler |
| Preprocessing | Log1p transform on Frequency & Monetary |

## ⚙️ Installation

### 1. Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/ecommerce-customer-segmentation.git
cd ecommerce-customer-segmentation
```

### 2. Create a virtual environment (recommended)

```bash
python -m venv venv
source venv/bin/activate        # Mac/Linux
venv\Scripts\activate           # Windows
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Download the dataset

Download `Online Retail.xlsx` from [UCI Repository](https://archive.ics.uci.edu/ml/datasets/Online+Retail), convert to CSV, and save as `data.csv` in the root directory.

---

## 🚀 Usage

### Run the full notebook

```bash
jupyter notebook notebooks/ecommerce_rfm_analysis.ipynb
```

### Get product recommendations

```python
# Item-based recommendation
recommend('WHITE HANGING HEART T-LIGHT HOLDER', n=5)

# Segment-based recommendation
recommend_for_segment(segment='VIP', n=5)
```

---

## 📁 Project Structure

```
ecommerce-customer-segmentation/
│
├── notebooks/
│   ├── ecommerce_rfm_analysis.ipynb   # Main analysis notebook
│   └── images/                         # Plot screenshots
│
├── data.csv                            # Dataset (not included — see above)
├── requirements.txt                    # Python dependencies
├── README.md                           # You are here
└── LICENSE
```

---

## 🛠️ Tech Stack

| Library | Purpose |
|---------|---------|
| `pandas` | Data manipulation |
| `numpy` | Numerical operations |
| `matplotlib` / `seaborn` | Visualization |
| `scikit-learn` | K-Means, StandardScaler, Silhouette Score, Cosine Similarity |

---

<p align="center">Made with ❤️ | Give it a ⭐ if you found it useful!</p>
