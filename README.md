🛒 E-Commerce Customer Segmentation & Product Recommendation
Show Image
Show Image
Show Image
Show Image
Show Image
Show Image

UK retail customer segmentation using RFM analysis & K-Means clustering, with a cosine similarity-based product recommendation system.


📌 Table of Contents

Overview
Dataset
Project Pipeline
Results & Visualizations
Installation
Usage
Project Structure
Tech Stack
Next Steps


🔍 Overview
This project analyzes a real-world UK-based online retail dataset to understand customer behavior and drive personalized marketing decisions.
Goals:

Clean and explore transactional e-commerce data
Build an RFM model to score and rank customers
Segment customers using K-Means Clustering
Build a Product Recommendation System using Cosine Similarity


📂 Dataset
Source: UCI Machine Learning Repository — Online Retail Dataset
ColumnDescriptionInvoiceNoUnique invoice ID — prefix C means cancelledStockCodeProduct codeDescriptionProduct nameQuantityUnits purchasedInvoiceDateDate & time of transactionUnitPricePrice per unit (GBP £)CustomerIDUnique customer identifierCountryCustomer's country

⚠️ Dataset is not included in this repo. Download it from the UCI link above and place it as data.csv in the root directory.


🗺️ Project Pipeline
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

📊 Results & Visualizations
Customer Segments
SegmentRecency (avg)Frequency (avg)Monetary (avg)Count🏆 VIPLowHighHigh~10%💙 LoyalMediumMedium-HighMedium-High~25%🟡 RegularMediumMediumMedium~40%❌ LostHighLowLow~25%
Clustering Performance
MetricValueAlgorithmK-Means (K=4)Silhouette Score0.383 ✅ AcceptableFeature ScalingStandardScalerPreprocessingLog1p transform on Frequency & Monetary
Sample Visualizations

📸 (Add screenshots of your plots here after running the notebook)
Suggested plots to screenshot and upload:

Correlation Heatmap
Elbow Method curve
Recency vs Monetary scatter plot (colored by cluster)
Segment distribution bar chart


notebooks/images/
├── heatmap.png
├── elbow_method.png
├── cluster_scatter.png
└── segment_distribution.png

⚙️ Installation
1. Clone the repository
bashgit clone https://github.com/YOUR_USERNAME/ecommerce-customer-segmentation.git
cd ecommerce-customer-segmentation
2. Create a virtual environment (recommended)
bashpython -m venv venv
source venv/bin/activate        # Mac/Linux
venv\Scripts\activate           # Windows
3. Install dependencies
bashpip install -r requirements.txt
4. Download the dataset
Download Online Retail.xlsx from UCI Repository, convert to CSV, and save as data.csv in the root directory.

🚀 Usage
Run the full notebook
bashjupyter notebook notebooks/ecommerce_rfm_analysis.ipynb
Get product recommendations
python# Item-based recommendation
recommend('WHITE HANGING HEART T-LIGHT HOLDER', n=5)

# Segment-based recommendation
recommend_for_segment(segment='VIP', n=5)

📁 Project Structure
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

🛠️ Tech Stack
LibraryPurposepandasData manipulationnumpyNumerical operationsmatplotlib / seabornVisualizationscikit-learnK-Means, StandardScaler, Silhouette Score, Cosine Similarity

🔮 Next Steps

 Try DBSCAN or Agglomerative Clustering and compare Silhouette Scores
 Add Apriori / Association Rules for richer product recommendations
 Build an interactive Streamlit dashboard for segment exploration
 Automate RFM refresh with a scheduled pipeline


📄 License
This project is licensed under the MIT License — see the LICENSE file for details.

<p align="center">Made with ❤️ | Give it a ⭐ if you found it useful!</p>
