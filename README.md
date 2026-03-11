# 🚗 Uber Customer Segmentation & Retention Analysis

Unsupervised machine learning project to identify distinct Uber customer segments and derive data-driven retention strategies using real rideshare data from Boston, MA.

---

## 📌 Project Overview

This project analyzes **500,000+ Uber ride records** to uncover hidden behavioral patterns among customers. Using KMeans clustering, four distinct customer segments were identified — each with unique pricing preferences, ride timing, and service tier choices. The findings were translated into actionable business retention recommendations.

---

## 📂 Dataset

- **Source:** [Uber & Lyft Dataset — Boston, MA](https://www.kaggle.com/datasets/brllrb/uber-and-lyft-dataset-boston-ma) (Kaggle)
- **Scope:** Uber rides only (filtered from combined Uber + Lyft data)
- **Features:** Price, distance, ride type, source/destination, timestamp, weather conditions

---

## 🛠️ Tech Stack

| Tool | Purpose |
|------|---------|
| Python | Core language |
| Pandas & NumPy | Data manipulation & feature engineering |
| Scikit-learn | KMeans clustering, StandardScaler, LabelEncoder |
| Matplotlib & Seaborn | Visualization |
| Kaggle Hub | Dataset download |

---

## 🔧 Project Structure

```
├── Uber_Customer_Segmentation.ipynb   # Main notebook
├── README.md                          # Project documentation
```

---

## 🧪 Methodology

### 1. Data Cleaning & EDA
- Filtered to Uber-only rides
- Identified and handled missing price values
- Checked for duplicates and data quality issues
- Explored ride type distribution and top pickup/drop-off locations

### 2. Feature Engineering
- Extracted time features: hour, day, month, day of week, weekend flag
- Created ride period buckets: Morning / Afternoon / Evening / Night
- Built price categories using quantile binning (Low / Medium / High)
- Label-encoded categorical columns (ride type, source, destination) for ML compatibility

### 3. KMeans Clustering
- Selected features: `price`, `hour`, `ride_type_encoded`, `source_encoded`, `destination_encoded`
- Applied **StandardScaler** to normalize features and prevent price from dominating distance calculations
- Used **Elbow Method** (k=1 to 10) to determine optimal **k=4**
- Assigned cluster labels back to the original dataset

### 4. Cluster Profiling & Visualization
- Scatter plots (price vs. hour by cluster)
- Heatmap of average feature values per segment
- Service type preferences per cluster
- Weekday vs. weekend ride distribution

### 5. Retention & Behavioral Analysis
- Daily and monthly ride volume trends
- Average price fluctuations over time
- Ride period preferences by segment
- Weekend vs. weekday breakdown per cluster

---

## 📊 Key Findings

| Cluster | Segment | Characteristics |
|---------|---------|-----------------|
| 0 | Budget Commuters | Low price, peak hours, UberX preference |
| 1 | Daytime Riders | Mid-range price, afternoon rides |
| 2 | Premium Users | High price, varied hours, premium services |
| 3 | Night Riders | Low-mid price, late night, weekend skew |

---

## 💡 Retention Recommendations

- **Night Riders** → High churn risk due to surge pricing sensitivity; consider late-night fare caps or promo codes
- **Premium Users** → Highest lifetime value (LTV); prioritize loyalty rewards and exclusive perks
- **Budget Commuters** → Most consistent segment; retain through price stability and commuter subscription plans
- **Daytime Riders** → Respond well to afternoon flash deals and destination-based discounts

---

## 🚀 How to Run

1. Clone this repository
   ```bash
   git clone https://github.com/YOUR_USERNAME/uber-customer-segmentation.git
   cd uber-customer-segmentation
   ```

2. Install dependencies
   ```bash
   pip install kagglehub pandas numpy scikit-learn matplotlib seaborn
   ```

3. Open the notebook
   ```bash
   jupyter notebook Uber_Customer_Segmentation.ipynb
   ```

> **Note:** A Kaggle API key is required to download the dataset via `kagglehub`. Set it up at [kaggle.com/settings](https://www.kaggle.com/settings).

---
