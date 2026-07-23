# House Price Prediction — King County Housing Dataset

<p align="center">
  <img src="https://img.shields.io/badge/Oasis_Infobyte-Data_Analytics-blue?style=for-the-badge" alt="Oasis Infobyte">
  <img src="https://img.shields.io/badge/Level-2-green?style=for-the-badge" alt="Level 2">
  <img src="https://img.shields.io/badge/Status-Completed-success?style=for-the-badge" alt="Status">
</p>

<p align="center">
  A complete end-to-end regression project that predicts residential house prices in King County, WA using tree-based ensemble models and linear regression.
</p>

---

## [DEMO: House Price Prediction - King County Dataset](https://github.com/Roopank26/OIBSIP/tree/main/DataAnalytics-L5-HousePricePrediction)

![Python](https://img.shields.io/badge/python-3.9%2B-blue)
![scikit-learn](https://img.shields.io/badge/scikit--learn-%F0%9F%A6%8D-orange)
![License](https://img.shields.io/badge/license-MIT-green)
![Made with Jupyter](https://img.shields.io/badge/made%20with-Jupyter-orange)

---

## Project Overview

This project was developed during the **Oasis Infobyte Data Analytics Internship (Level 2)**. The objective was to build a complete machine learning regression pipeline capable of estimating residential property prices based on structural and locational features.

I did not just chase a high R² score. I treated this like a real-world consulting assignment: exploring distributions, questioning outliers, engineering features that make sense to a homeowner, and interpreting model outputs in plain English.

---

## Dataset Description

| Attribute | Value |
|-----------|-------|
| **Name** | King County House Sales |
| **Records** | 21,613 homes sold between May 2014 – May 2015 |
| **Region** | King County, Washington (includes Seattle) |
| **Source** | IBM Skills Network Public Mirror |
| **Features** | 21 variables (after preprocessing) |
| **Target** | `price` — sale price in USD |

**Key features used in modeling:**
- `sqft_living` / `total_sqft` — indoor living space
- `grade` — construction quality (1–13 scale)
- `lat` / `long` — geographic coordinates
- `bedrooms`, `bathrooms`, `floors`
- `waterfront` — binary exposure flag
- `house_age`, `renovated`, `has_basement`

---

## Technologies Used

- **Python 3.9+**
- **Pandas** — data manipulation & cleaning
- **NumPy** — numerical operations
- **Matplotlib & Seaborn** — visualization
- **Scikit-learn** — modeling, evaluation, train/test split

---

## Machine Learning Workflow

1. **Data Loading** — loaded `dataset.csv`, inspected shape, dtypes, and first/last rows
2. **Data Exploration** — missing value analysis, duplicate check, target distribution
3. **Data Cleaning** — removed index artifacts, parsed dates, capped price outliers via IQR
4. **Feature Engineering** — created `house_age`, `renovated`, `has_basement`, `total_sqft`
5. **Exploratory Data Analysis** — correlation heatmap, pairplot, boxplots, scatter plots
6. **Train/Test Split** — 80/20 split, `random_state=42`
7. **Model Training** — Linear Regression, Random Forest (200 trees, depth 12), Gradient Boosting (200 trees, depth 4, lr=0.05)
8. **Model Evaluation** — MAE, MSE, RMSE, R² Score
9. **Feature Importance** — analyzed via Random Forest and Gradient Boosting
10. **Prediction Visualization** — actual vs predicted, residuals, error distribution
11. **Error Analysis** — examined worst predictions and discussed root causes
12. **Business Insights** — translated model results into seller/buyer recommendations

---

## Model Comparison

| Model | R² Score | MAE ($) | RMSE ($) |
|-------|----------|---------|----------|
| Linear Regression | 0.7415 | 94,654 | 126,537 |
| Random Forest | **0.8906** | **56,513** | **82,318** |
| Gradient Boosting | 0.8872 | 58,380 | 83,592 |

**Best Model:** **Random Forest Regressor** — achieved the highest R² of 0.8906 while maintaining the lowest MAE and RMSE. Gradient Boosting was close behind at 0.8872, and both dramatically outperformed the linear baseline.

---

## Key Findings

- **Grade** is the single strongest predictor (importance: 0.32). Moving a home up one grade level can add tens of thousands of dollars.
- **Latitude** ranked second (0.29), which is interesting — within King County, north-south location matters almost as much as build quality.
- **Total square footage** and **living space** together contribute ~24% of predictive power.
- **Waterfront** exposure, despite being a binary variable, carries a massive premium (>$1M on average).
- **Condition** is surprisingly weak — cosmetic condition matters less than structural grade or size.
- **Bedrooms** and **bathrooms** individually show low importance; what matters is overall space and quality.

---

## Results & Visualizations

All plots are saved in the `images/` directory.

| Visualization | Description |
|---------------|-------------|
| `target_distribution.png` | Histogram of sale prices — heavy right skew |
| `missing_values.png` | Missing value heatmap (clean dataset) |
| `correlation_heatmap.png` | Pearson correlations across numerical features |
| `pairplot_sample.png` | Pairwise relationships for key variables |
| `condition_boxplot.png` | Price spread across house conditions |
| `waterfront_boxplot.png` | Price comparison: waterfront vs inland |
| `scatter_sqft_price.png` | Price vs living space, colored by grade |
| `feature_importance.png` | Random Forest & Gradient Boosting importance |
| `actual_vs_predicted.png` | Predicted vs actual scatter (Random Forest) |
| `residual_plot.png` | Residuals across prediction range |
| `prediction_error_distribution.png` | Histogram of prediction errors |
| `model_performance.png` | Side-by-side metric comparison |

---

## Installation

```bash
git clone https://github.com/Roopank26/OIBSIP.git
cd OIBSIP/DataAnalytics-L5-HousePricePrediction
pip install -r requirements.txt
```

---

## Usage

Open the notebook in Jupyter:

```bash
jupyter notebook House_Price_Prediction.ipynb
```

Run all cells from top to bottom. The notebook is self-contained — it will load the dataset, generate all visualizations, train the models, and save the plots to `./images/`.

---

## Business Insights

**For sellers:**
- Prioritize grade-quality finishes. A kitchen or bathroom upgrade that bumps a home from grade 6 to grade 7 can increase price by $80k–$120k on average.
- If the home is near water, make that the headline of any listing. The waterfront premium is substantial.

**For buyers:**
- Do not overpay for cosmetic condition. Focus on the grade score and total square footage instead.
- More bedrooms beyond 3–4 do not add proportional value. Bathrooms retain value better than bedrooms.

**For investors:**
- Look for undervalued homes near water that have not been renovated. There is clear renovation upside on top of location premium.
- Latitude matters a lot in King County — the right neighborhood is half the battle.

---

## Limitations & Future Work

- Dataset is from **2014–2015**; current market dynamics are different.
- No macroeconomic variables (interest rates, inventory) were included.
- School district quality and crime rates could add significant predictive power.
- **Future improvements:** add XGBoost or LightGBM, apply log-transform to price, tune hyperparameters via GridSearchCV, and introduce geospatial clustering for neighborhood tiers.

---

## Project Structure

```
DataAnalytics-L5-HousePricePrediction/
├── dataset.csv
├── House_Price_Prediction.ipynb
├── requirements.txt
├── README.md
├── LICENSE
└── images/
    ├── target_distribution.png
    ├── missing_values.png
    ├── correlation_heatmap.png
    ├── pairplot_sample.png
    ├── condition_boxplot.png
    ├── waterfront_boxplot.png
    ├── scatter_sqft_price.png
    ├── bedroom_countplot.png
    ├── feature_importance.png
    ├── actual_vs_predicted.png
    ├── residual_plot.png
    ├── prediction_error_distribution.png
    └── model_performance.png
```

---

## Author

**Roopank Kala**  
Data Analytics Intern at Oasis Infobyte  
[GitHub @Roopank26](https://github.com/Roopank26)

---

## License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.

---

> *“The goal wasn't just to hit a good R² score — it was to understand what actually drives home values in a real market.”*
