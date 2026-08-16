# 3mtt-Capstone-Project
# Retail Customer Segmentation – Alheri Supermarket

## Project Overview

This project segments customers of **Alheri Supermarket** (Nigerian retail context) using RFM (Recency, Frequency, Monetary) analysis and K-Means clustering. The goal is to enable targeted marketing, improve customer retention, and optimise resource allocation for the retail business.

## Business Problem

Nigerian retailers often treat all customers uniformly, missing opportunities for:
- **Personalised marketing** campaigns
- **Customer retention** and loyalty building
- **Resource optimisation** by focusing on high-value segments

## Solution

The solution uses:
- **RFM Analysis**: Quantifies customer value based on Recency, Frequency, and Monetary metrics
- **K-Means Clustering**: Groups similar customers into 4 distinct segments
- **Actionable Insights**: Segment-specific marketing strategies

---

## Dataset

| Attribute | Value |
|-----------|-------|
| **Source** | Simulated transaction data based on real Nigerian market prices (2025) |
| **Size** | 657,531 transactions |
| **Unique Customers** | 2,500 |
| **Period** | January – December 2025 |
| **Total Revenue** | ₦15,856,321,170.00 |
| **Avg Basket Size** | 3.89 items per transaction |
| **Bulk Purchase Ratio** | 3.04% |

### Product Categories
The data includes transactions across 7 categories:
- Foodstuff (40%)
- Beverages (25%)
- Household (15%)
- Electronics (5%)
- Clothing (5%)
- Phone Accessories (5%)
- Baby Items (5%)

---

## Methodology

### Step 1: Data Generation & Cleaning
- Generated realistic transaction data based on Nigerian market prices
- Removed negative quantities and outliers
- Created transaction-level features (TotalPrice, Month, etc.)

### Step 2: Exploratory Data Analysis (EDA)
- Analysed revenue distribution by category
- Identified monthly sales trends
- Visualised transaction patterns and customer behaviour

### Step 3: RFM Analysis
Calculated for each customer:
- **Recency (R)**: Days since last purchase
- **Frequency (F)**: Total number of purchases
- **Monetary (M)**: Total money spent
- **Additional metrics**: Average basket size, bulk purchase ratio, preferred category

### Step 4: Feature Scaling
- Applied StandardScaler to RFM features for clustering
- Used Log transformation on Monetary to handle skew

### Step 5: Clustering
- Applied K-Means clustering with optimal k=4 (determined via Elbow method and Silhouette score)
- Validated with Silhouette Score = 0.4616

### Step 6: Segment Profiling
- Analysed each cluster's characteristics
- Named segments based on behaviour patterns
- Generated business recommendations

---

## Key Findings

### Model Evaluation Metrics
| Metric | Value |
|--------|-------|
| **Optimal Clusters** | 4 |
| **Silhouette Score** | 0.4616 |
| **Total Customers** | 2,500 |
| **Average Recency** | 10.54 days |
| **Average Frequency** | 284.44 purchases |
| **Average Monetary** | ₦6,342,528.47 |

### Segment Profiles

| Segment | Size | Avg Recency | Avg Frequency | Avg Spend | Top Category | Strategy |
|---------|------|-------------|---------------|-----------|--------------|----------|
|  **Loyal** | ~11% | 4 days | 850 purchases | ₦19,081,080 | Foodstuff | VIP loyalty, exclusive access, personal shopping |
|  **Potential Loyal** | ~27% | 4 days | 375 purchases | ₦8,221,309 | Foodstuff | Upsell/cross-sell, loyalty program invitations |
|  **At Risk** | ~38% | 62 days | 59 purchases | ₦1,191,601 | Foodstuff | Re-engagement campaigns, win-back offers |
|  **New & Infrequent** | ~24% | 3 days | 850 purchases | ₦19,081,080 | Foodstuff | Welcome offers, first-purchase discounts, email nurturing |

### Category Preferences by Segment

The heatmap analysis reveals:
- **Foodstuff** is the dominant category across all segments (98.8%+)
- **Beverages** shows slight preference among At Risk customers
- **Household** and **Electronics** are niche categories

### Average Basket Size
| Segment | Avg Basket Size |
|---------|-----------------|
| Champions | ~4.9 items |
| Potential Loyal | ~4.0 items |
| At Risk | ~3.9 items |
| New & Infrequent | ~4.5 items |

---

## Business Recommendations

1. **Marketing Budget Allocation**
   - Focus 60% of marketing budget on **Champions** and **Potential Loyal** customers

2. **Loyalty Program**
   - Launch a VIP loyalty program for the Champion segment (≈275 customers)
   - Offer exclusive access, early product releases, and personal shopping assistance

3. **Re-engagement Campaigns**
   - Target At Risk customers (≈950 customers) with:
     - Win-back offers and special discounts
     - SMS/WhatsApp campaigns with personalised deals
     - Surveys to understand why they stopped visiting

4. **New Customer Nurturing**
   - Implement welcome sequences for New & Infrequent customers
   - Offer first-purchase discounts and cross-sell popular items

5. **Category-Based Personalisation**
   - Leverage category preferences for personalised promotions
   - Champions show preference for Foodstuff and Beverages
   - At Risk customers respond better to Beverages promotions

6. **Bulk Purchase Strategy**
   - Bulk buyers account for 3.04% of transactions
   - Offer bulk discounts and bundle deals to encourage larger basket sizes

---


---

## Visualisation Summary

### EDA Visualisations
- Revenue by Category: Foodstuff dominates with 95.8% of revenue
- Transaction Distribution: Most transactions under ₦20,000
- Monthly Sales Trend: Consistent growth throughout 2025
- Top Customers: Top 10 customers account for significant revenue

### Cluster Evaluation
- **Elbow Method**: Optimal k=4 identified
- **Silhouette Score**: 0.4616 indicates decent clustering quality
- **Calinski-Harabasz**: Confirms cluster separation
- **Davies-Bouldin**: Lower score indicates better clustering

### Segment Visualisations (PCA)
- Clear separation between segments in 2D PCA space
- Champions cluster shows high frequency and monetary values
- At Risk customers cluster with high recency values

