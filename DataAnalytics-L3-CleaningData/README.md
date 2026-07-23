# Cleaning Data

<p align="center">
  <img src="https://img.shields.io/badge/Oasis_Infobyte-Internship-green?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Data_Analytics-Task_3-blue?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Python-3.13%2B-orange?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Pandas-2.3-blue?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Seaborn-0.13-teal?style=for-the-badge" />
</p>

## Overview

This project demonstrates a **production-quality data cleaning pipeline** developed as part of the **Oasis Infobyte Data Analytics Internship (Level 3)**. The goal is to take a raw, messy dataset, clean it thoroughly, document every preprocessing step, and generate a cleaned dataset ready for analysis or machine learning.

## Objective

- Load and inspect a raw dataset containing common data quality issues.
- Handle missing values using appropriate imputation strategies.
- Remove duplicate rows.
- Standardize and clean inconsistent text data.
- Convert data types to their proper formats.
- Detect and handle outliers using the IQR method.
- Remove invalid/impossible entries.
- Rename columns for clarity.
- Validate the final dataset.
- Save the cleaned dataset and generate professional visualizations.

## Dataset Description

- **Name:** Hotel Booking Dataset (Synthetic)
- **Rows:** 2,500
- **Columns:** 31
- **Features include:** Customer demographics, booking dates, stay details, revenue, ratings, loyalty points, agent/company IDs, and more.
- **Issues introduced:** Missing values, duplicates, mixed text cases, invalid dates, negative values, and extreme outliers.

## Technologies Used

| Tool | Version |
|------|---------|
| Python | 3.13+ |
| Pandas | 2.3.3 |
| NumPy | 2.4.6 |
| Matplotlib | 3.11.0 |
| Seaborn | 0.13.2 |
| Jupyter | 1.1.1 |

## Project Structure

```
DataAnalytics-L3-CleaningData/
├── dataset.csv                          # Raw input dataset
├── cleaned_dataset.csv                  # Final cleaned dataset
├── Cleaning_Data.ipynb                  # Jupyter Notebook with full pipeline
├── requirements.txt                     # Python dependencies
├── README.md                            # Project documentation
├── LICENSE                              # MIT License
├── __init__.py                          # Package initializer
└── images/
    ├── missing_values_before.png         # Heatmap before cleaning
    ├── missing_values_after.png          # Heatmap after cleaning
    ├── boxplot_before.png                # Boxplot before cleaning
    ├── boxplot_after.png                 # Boxplot after cleaning
    ├── distribution_plots.png            # Histograms & KDEs
    ├── correlation_heatmap.png           # Feature correlations
    └── final_dataset_preview.png         # Cleaned dataset preview table
```

## Cleaning Steps

### 1. Import Libraries
Loaded `pandas`, `numpy`, `matplotlib`, and `seaborn` for data manipulation and visualization.

### 2. Load Dataset
Loaded `dataset.csv`, displayed first/last 5 rows, shape (2500x31), and column names.

### 3. Initial Dataset Inspection
- Used `.info()` to inspect datatypes and non-null counts.
- Used `.describe()` for statistical summary.
- Calculated missing values per column.
- Found **75 duplicated rows**.
- Identified mixed datatypes (dates stored as strings, binary columns as text).
- Captured memory usage (~2.84 MB).

### 4. Missing Value Handling
Applied context-aware imputation:
- **Median** for numerical columns with outliers (`Age`, `ADR`).
- **Mode** for categorical columns (`Country`, `Gender`, `Meal_Type`).
- **Zero** for counts/points (`Loyalty_Points`, `Special_Requests`).
- **'Unknown'** for identifiers (`Agent_ID`).
- **Dropped** rows missing critical identifiers (`customer_id`, `Name`, `email`, dates).

### 5. Duplicate Removal
- **Before:** 75 duplicate rows.
- **After:** 0 duplicate rows.
- **Removed:** 75 rows.

### 6. Standardize Text Data
- Converted categorical text to **Title Case**.
- Trimmed whitespace.
- Fixed inconsistent spellings (`USA`, `United Kingdom`, `Germany`, `Portugal`).
- Standardized gender (`M` → `Male`, `F` → `Female`).

### 7. Data Type Conversion
- Converted `Booking_Date`, `Check_In`, `Check_Out` from `object` to `datetime64[ns]`.
- Converted numeric columns using `pd.to_numeric`.
- Converted `Parking_Space` to binary (0/1).
- Converted `Is_Repeated_Guest` to nullable integer (`Int64`).
- Dropped 4 rows with invalid/unparseable dates.

### 8. Outlier Detection
Applied the **IQR method (1.5 × IQR rule)** on key numerical columns:
- `Age`, `ADR`, `Total_Nights`, `Lead_Time`, `Total_Revenue`, `Previous_Cancellations`, `Review_Score`, `Loyalty_Points`.
- Outliers were **capped** (not removed) to preserve data volume.

### 9. Invalid Data Handling
Removed logically impossible values:
- **3** invalid ages (<=0 or >100).
- **196** negative ADR values.
- **195** negative `Total_Nights`.
- **1** negative `Lead_Time`.

### 10. Rename Columns
Renamed key columns for consistency:
- `customer_id` → `Customer_ID`
- `Name` → `Customer_Name`
- `email` → `Email`
Reordered columns into a logical sequence.

### 11. Final Dataset Validation
- **Duplicates:** 0
- **Missing values:** Reduced significantly; remaining NaNs are in optional fields.
- **Datatypes:** All correct.
- **Column names:** Clean and consistent.

### 12. Save Clean Dataset
Exported the final cleaned dataset to `cleaned_dataset.csv`.

### 13. Final Summary

| Metric | Value |
|--------|-------|
| Original Rows | 2,500 |
| Final Rows | 2,029 |
| Rows Removed | 471 |
| Duplicates Removed | 75 |
| Invalid Data Removed | 396 |
| Missing Values Handled | Multiple columns |
| Datatype Conversions | 8 columns |
| Outliers Treated | 8 columns |

## Results

- **Cleaned Dataset:** `cleaned_dataset.csv` (2,029 rows × 31 columns)
- **Visualizations:** 7 professional plots saved in `images/`
- **Notebook:** Fully executable `Cleaning_Data.ipynb` with markdown explanations for every step

## Screenshots

| Visualization | Preview |
|---------------|---------|
| Missing Values (Before) | `images/missing_values_before.png` |
| Missing Values (After) | `images/missing_values_after.png` |
| Boxplot (Before) | `images/boxplot_before.png` |
| Boxplot (After) | `images/boxplot_after.png` |
| Distributions | `images/distribution_plots.png` |
| Correlation | `images/correlation_heatmap.png` |
| Final Preview | `images/final_dataset_preview.png` |

## How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/roopank/OIBSIP_DataAnalytics_L3_CleaningData.git
   cd OIBSIP_DataAnalytics_L3_CleaningData
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Open the notebook:
   ```bash
   jupyter notebook Cleaning_Data.ipynb
   ```

4. Run all cells sequentially to reproduce the cleaning pipeline and visualizations.

## Requirements

```
pandas
numpy
matplotlib
seaborn
jupyter
```

## Future Improvements

- Apply advanced imputation (`IterativeImputer`, `KNNImputer`) for missing values.
- Use encoding strategies for categorical variables before ML modeling.
- Add automated data quality reports with `ydata-profiling`.
- Implement version control for datasets using `DVC`.
- Extend cleaning pipeline to handle streaming data.

## Author

**Roopank**  
Oasis Infobyce Data Analytics Intern  
[LinkedIn](https://www.linkedin.com/) | [GitHub](https://github.com/roopank)

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
