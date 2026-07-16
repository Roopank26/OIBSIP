# DataAnalytics-L1-EDARetailSales
### Oasis Infobyte Data Analytics Internship | Level 1 | EDA Retail Sales

---

## Project Overview

This project performs comprehensive Exploratory Data Analysis (EDA) on a retail sales dataset to uncover actionable business insights. The analysis covers sales, profit, quantity, discounts, categories, regions, customer segments, and temporal trends.

## Objectives

- Understand the structure and quality of the retail sales dataset
- Identify key patterns and anomalies in sales, profit, and discount metrics
- Analyze category-wise, region-wise, and customer-wise performance
- Deliver data-driven recommendations for business growth

## Dataset

The dataset (`data/retail_sales.csv`) contains **5,075 records** with the following attributes:

| Column | Description |
|--------|-------------|
| Order ID | Unique order identifier |
| Order Date | Date the order was placed |
| Ship Date | Date the order was shipped |
| Customer Name | Name of the customer |
| Segment | Customer segment (Consumer, Corporate, Home Office) |
| Region | Geographic region (North, South, East, West) |
| State | U.S. state |
| Category | Product category |
| Sub-Category | Product sub-category |
| Sales | Sales amount |
| Quantity | Units sold |
| Discount | Discount applied |
| Profit | Profit earned |

## Technologies Used

- Python 3.10+
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Plotly
- Jupyter Notebook

## Folder Structure

```
DataAnalytics-L1-EDARetailSales/
├── data/
│   └── retail_sales.csv
├── notebook/
│   └── Retail_Sales_EDA.ipynb
├── outputs/
│   ├── sales_distribution.png
│   ├── profit_distribution.png
│   ├── monthly_sales_trend.png
│   ├── monthly_profit_trend.png
│   ├── category_sales.png
│   ├── subcategory_sales.png
│   ├── regional_sales.png
│   ├── state_sales.png
│   ├── top_customers.png
│   ├── discount_vs_profit.png
│   ├── correlation_heatmap.png
│   └── pairplot.png
├── reports/
│   └── Retail_Sales_EDA_Report.pdf
├── README.md
├── requirements.txt
└── LICENSE
```

## Installation Steps

```bash
git clone https://github.com/Roopank26/OIBSIP.git
cd OIBSIP/DataAnalytics-L1-EDARetailSales
pip install -r requirements.txt
```

## How to Run

```bash
jupyter notebook notebook/Retail_Sales_EDA.ipynb
```

Run all cells sequentially to perform analysis and generate visualizations.

## Key Findings

- **Furniture** category leads in sales but has lower profit margins due to high discounts
- **West Region** outperforms other regions in both sales and profitability
- **Consumer Segment** drives the highest volume of orders
- **Discounts above 30%** correlate with negative profits
- **Technology Sub-Category** (Phones) shows the highest profit margins

## Future Improvements

- Build predictive models for sales forecasting
- Integrate customer lifetime value (CLV) analysis
- Add interactive dashboards using Plotly Dash or Streamlit
- Incorporate external economic indicators for deeper insights
- Perform cohort analysis on customer retention

## Author

**Roopank**  
Data Analytics Intern | Oasis Infobyte  
GitHub: [@Roopank26](https://github.com/Roopank26)

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
