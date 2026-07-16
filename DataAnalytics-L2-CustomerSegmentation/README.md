# Customer Segmentation Analysis

**Oasis Infobyte Data Analytics Internship**  
**Track:** Data Analytics | **Level:** L2  
**Project:** Customer Segmentation Analysis

![Python](https://img.shields.io/badge/python-3.9%2B-blue)
![Pandas](https://img.shields.io/badge/pandas-latest-green)
![Scikit-learn](https://img.shields.io/badge/scikit--learn-latest-orange)
![Matplotlib](https://img.shields.io/badge/matplotlib-latest-red)

---

## Project Overview

This project performs **customer segmentation analysis** on mall customer data using **K-Means clustering**. The goal is to identify distinct customer segments based on demographic and behavioral attributes, enabling data-driven marketing strategies and personalized customer experiences.

By understanding customer segments, businesses can optimize marketing spend, improve customer retention, and maximize lifetime value (LTV).

---

## Objectives

- Analyze mall customer data to identify natural segments
- Determine the optimal number of clusters using Elbow Method and Silhouette Score
- Interpret cluster characteristics and assign meaningful labels
- Provide actionable business recommendations for each segment
- Generate publication-ready visualizations and a comprehensive PDF report

---

## Dataset

**File:** `data/Mall_Customers.csv`  
**Records:** 200 customers  
**Features:** 5 attributes

| Feature | Description |
|---------|-------------|
| CustomerID | Unique identifier for each customer |
| Gender | Male or Female |
| Age | Customer age (18-70 years) |
| Annual Income (k$) | Annual income in thousands of dollars |
| Spending Score (1-100) | Score assigned based on customer spending behavior |

---

## Technologies

- **Python 3.9+**
- **Pandas** - Data manipulation and analysis
- **NumPy** - Numerical computations
- **Matplotlib** - Data visualization
- **Seaborn** - Statistical data visualization
- **Scikit-learn** - Machine learning (KMeans, StandardScaler, metrics)
- **Plotly** - Interactive visualizations (optional)
- **Jupyter Notebook** - Interactive analysis environment

---

## Installation

### Prerequisites
- Python 3.9 or higher
- pip package manager

### Setup

```bash
# Clone the repository
git clone https://github.com/<your-username>/DataAnalytics-L2-CustomerSegmentation.git
cd DataAnalytics-L2-CustomerSegmentation

# Install dependencies
pip install -r requirements.txt

# Launch Jupyter Notebook
jupyter notebook
```

---

## Folder Structure

```
DataAnalytics-L2-CustomerSegmentation/
│
├── data/
│   └── Mall_Customers.csv
│
├── notebook/
│   └── Customer_Segmentation.ipynb
│
├── outputs/
│   ├── customer_distribution.png
│   ├── age_distribution.png
│   ├── income_distribution.png
│   ├── spending_distribution.png
│   ├── gender_distribution.png
│   ├── correlation_heatmap.png
│   ├── elbow_method.png
│   ├── silhouette_scores.png
│   ├── customer_clusters.png
│   ├── cluster_centroids.png
│   ├── pairplot.png
│   └── cluster_profile.png
│
├── reports/
│   └── Customer_Segmentation_Report.pdf
│
├── README.md
├── requirements.txt
└── LICENSE
```

---

## Notebook Sections

The Jupyter Notebook (`notebook/Customer_Segmentation.ipynb`) contains 20 professionally structured sections:

1. Project Introduction
2. Business Objective
3. Dataset Description
4. Import Libraries
5. Load Dataset
6. Data Inspection
7. Missing Value Analysis
8. Duplicate Check
9. Data Cleaning
10. Exploratory Data Analysis
11. Feature Engineering
12. Feature Scaling using StandardScaler
13. Correlation Analysis
14. Elbow Method
15. Silhouette Score Evaluation
16. K-Means Clustering
17. Cluster Visualization
18. Cluster Interpretation
19. Business Recommendations
20. Conclusion

---

## Results

### Optimal Clusters: **K = 5**

| Cluster | Typical Age | Income Level | Spending Score | Segment Name |
|---------|-------------|--------------|----------------|--------------|
| 0 | ~60 years | Low (~38k$) | ~44 | Conservative Middle-Aged Savers |
| 1 | ~29 years | Moderate (~56k$) | ~54 | Young Balanced Spenders |
| 2 | ~60 years | High (~103k$) | ~35 | Older Affluent Conservative |
| 3 | ~34 years | High (~119k$) | ~45 | Young Affluent High-Spenders |
| 4 | ~50 years | Moderate (~68k$) | ~64 | Middle-Aged High-Value Loyal |

### Key Findings

- **Female customers** form the majority (52.5%) of the customer base
- **Age distribution** spans 18-70 years with a mean of 46.3 years, indicating a diverse audience
- **Annual income** ranges from 15k$ to 139k$, with most customers in the 40k$-90k$ range
- **Spending scores** range from 17 to 74, showing diverse spending behaviors
- **Weak correlations** between features confirm independent aspects of customer behavior, validating clustering approach

---

## Visualizations

All visualizations are saved in the `outputs/` folder at high resolution (150 DPI):

| Visualization | Description |
|---------------|-------------|
| `customer_distribution.png` | Overview of all key distributions |
| `gender_distribution.png` | Gender composition pie chart |
| `age_distribution.png` | Age histogram and boxplot by gender |
| `income_distribution.png` | Income histogram and boxplot by gender |
| `spending_distribution.png` | Spending score histogram and boxplot |
| `correlation_heatmap.png` | Feature correlation matrix |
| `elbow_method.png` | WCSS vs K plot for optimal cluster selection |
| `silhouette_scores.png` | Silhouette score evaluation for different K values |
| `customer_clusters.png` | Scatter plot of clusters (Income vs Spending) |
| `cluster_centroids.png` | Bar chart comparing cluster centroids |
| `pairplot.png` | Pairwise relationships colored by cluster |
| `cluster_profile.png` | Mean feature values by cluster |

---

## Cluster Summary & Business Insights

### Cluster 0 - Conservative Middle-Aged Savers (~60 years, Low Income, Low Spending)
- **Business Value:** Price-sensitive segment representing 20% of customers
- **Strategy:** Value bundles, family packages, off-peak discounts, and loyalty cards

### Cluster 1 - Young Balanced Spenders (~29 years, Moderate Income, Moderate Spending)
- **Business Value:** Growth potential segment with increasing purchasing power (17.5%)
- **Strategy:** Points-based loyalty, seasonal promotions, cross-selling, flexible payments

### Cluster 2 - Older Affluent Conservative Customers (~60 years, High Income, Low Spending)
- **Business Value:** High income but underutilized spending potential (20%)
- **Strategy:** Premium delivery, senior-friendly services, white-glove service, luxury catalogs

### Cluster 3 - Young Affluent High-Spenders (~34 years, High Income, High Spending)
- **Business Value:** Most valuable segment driving premium revenue (25%)
- **Strategy:** VIP memberships, luxury partnerships, concierge services, exclusive events

### Cluster 4 - Middle-Aged High-Value Loyal Customers (~50 years, Moderate Income, High Spending)
- **Business Value:** High-value loyal segment with strong CLV (17.5%)
- **Strategy:** Premium rewards, early access, personalized recommendations, member events

---

## Business Recommendations

1. **Personalized Marketing:** Use cluster assignments to tailor all marketing communications by segment
2. **Dynamic Pricing:** Adjust pricing strategies based on segment price sensitivity
3. **Store Layout:** Optimize product placement based on which clusters frequent specific areas
4. **Inventory Management:** Stock products aligned with each segment's preferences
5. **Customer Retention:** Develop segment-specific retention programs to maximize CLV

---

## How to Reproduce

1. Ensure all dependencies are installed (`pip install -r requirements.txt`)
2. Open `notebook/Customer_Segmentation.ipynb` in Jupyter
3. Run all cells sequentially (Cell > Run All)
4. All visualizations will be saved to `outputs/`
5. The notebook is fully reproducible with the provided dataset

---

## Report

A comprehensive PDF report is available at `reports/Customer_Segmentation_Report.pdf`, containing:
- Executive Summary
- Dataset Overview
- Methodology
- EDA with visualizations
- Clustering Process
- Cluster Interpretation
- Business Recommendations
- Conclusion

---

## Future Improvements

- Integrate real-time transaction data for dynamic segmentation
- Implement additional clustering algorithms (DBSCAN, Hierarchical, Gaussian Mixture)
- Build a customer segmentation prediction API
- Add time-series analysis for customer migration between segments
- Implement A/B testing framework for segment-specific campaigns
- Integrate with CRM systems for automated targeting
- Use deep learning approaches for high-dimensional customer data

---

## Author

**Data Science Team**  
Oasis Infobyte Data Analytics Internship  
Project: Customer Segmentation Analysis

---

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## Acknowledgments

- Dataset: Popular Mall Customers dataset (Kaggle/UCI)
- Internship Program: Oasis Infobyte Data Analytics Internship
- Tools: Python, Pandas, Scikit-learn, Matplotlib, Seaborn, ReportLab
