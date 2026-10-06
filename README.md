![Walmart](Walmart.jpg)
# Walmart Sales Statistical Analysis — CPI, Holidays, and Linear Regression

## Overview
This is a legacy educational statistical analysis and regression project exploring a historical Walmart weekly sales dataset. The project investigates the relationships between macroeconomic indicators, holiday events, and store sales. The primary objective was to perform exploratory data analysis (EDA), hypothesis testing, and fit a basic multiple linear regression model to better understand what drives variations in weekly sales.

## Questions Explored
- Are weekly sales materially different during holiday periods compared to non-holiday periods?
- How are the Consumer Price Index (CPI) and Holiday_Flag associated with Weekly_Sales?
- How much variation in weekly sales does a simple regression specification explain?

## Dataset
- **Size:** 6,435 rows and 8 columns
- **Stores:** 45 unique Walmart stores
- **Date Range:** February 5, 2010, through October 26, 2012
- **Key Variables:** `Store`, `Date`, `Weekly_Sales` (Target), `Holiday_Flag`, `Temperature`, `Fuel_Price`, `CPI`, and `Unemployment`
- **Source:** [Walmart Dataset on Kaggle](https://www.kaggle.com/datasets/yasserh/walmart-dataset)

## Analysis
The notebook implements the following analysis workflow:
- **Data Cleaning & Preprocessing:** Formatting dates and removing outliers using a 1.5 × IQR filter across multiple numeric columns (reducing the dataset from 6,435 to 5,923 observations).
- **Exploratory Data Analysis (EDA):** Visualizing sales distributions, seasonal trends, and variable correlations.
- **Hypothesis Testing:** Applying a Welch's two-sample t-test to evaluate the difference between holiday and non-holiday sales.
- **Modeling:** Fitting an Ordinary Least Squares (OLS) regression using the `statsmodels` library.

## Regression Result
The regression model used the following specification:

`Weekly_Sales ~ CPI + Holiday_Flag`

**Result:** The fitted model produced an **R² of 0.008**.

This means the model explains less than 1% of the variation in weekly sales, indicating that CPI and the binary holiday flag alone provide very limited explanatory power for this dataset. The notebook reports only in-sample model fit and does not evaluate predictive performance on unseen data.

## Key Takeaways
- **Hypothesis Testing:** The t-test (p-value 0.087) did not provide sufficient evidence to conclude that weekly sales differ significantly between holiday and non-holiday periods in this pooled dataset.
- **Model Fit Interpretation:** The extremely low R² demonstrates the limitations of a simplistic model. A weak regression result is valuable evidence indicating that the selected predictors are insufficient to fully capture the complexity of retail sales.
- **Fundamentals:** This project demonstrates practical application of introductory statistical analysis and hypothesis testing in Python.

## Limitations
- **No Holdout Evaluation:** There is no time-based or random train/test split. The model is entirely an in-sample exploratory regression, not a validated predictive model.
- **No Future Forecasting:** The project does not implement genuine out-of-sample future forecasting.
- **Omitted Variables:** Important temporal structures (seasonality, trend) and store-level heterogeneity (differences between individual stores) were not modeled in the final regression specification.
- **Environment Dependency:** The Jupyter notebook was originally authored for Google Colab and currently relies on a Colab-specific hardcoded file path (`/content/Walmart.csv`) to load the dataset.

## Resources
- **Google Colab Notebook:** [Walmart Regression Model.ipynb](https://colab.research.google.com/drive/14tVJZFwvJ3PwnEJwZx3u00WJjXwBN2Qy?usp=sharing)
- **Medium Article:** [Regression Analysis on Walmart Sales](https://medium.com/@farizalfitraaa/regression-analysis-on-walmart-sales-analyzing-the-impact-of-cpi-and-holiday-d68586a728b7)

## Project Context
This is a legacy educational project focusing on the fundamentals of exploratory data analysis, hypothesis testing, and interpreting linear regression outputs. It serves as a foundational exercise in statistical programming rather than a production-grade forecasting system. The findings accurately reflect the limitations of basic models when applied to complex, multidimensional retail data.
