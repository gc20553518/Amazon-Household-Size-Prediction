# Amazon-Household-Size-Prediction

**UCLA STATS 101C | Independent Machine Learning Project | Summer 2026**

## Project Overview

This project predicts household size using Amazon purchase history data. The goal is to explore whether purchasing behavior, such as spending patterns, product categories, and order frequency, can help estimate the number of people in a household.

The project was completed independently using R, covering data preprocessing, exploratory data analysis, feature engineering, model development, and evaluation.

## Dataset

- **1,850,717** Amazon purchase records
- **5,027** survey respondents
- **3,027** labeled training observations
- **2,000** unlabeled test observations

Purchase histories were aggregated at the respondent level to create behavioral predictors.

The original datasets are not included in this repository.

## Methods & Tools

**Language:** R

**Libraries:** data.table, dplyr, ggplot2, glmnet, randomForest, gbm

**Methods:**
- Data cleaning and exploratory data analysis
- Behavioral feature engineering
- Random forest feature importance
- Ridge and Lasso regression
- Random Forest and Gradient Boosting
- 5-fold cross-validation
- Root Mean Squared Error (RMSE)

## Feature Engineering

Engineered over 180 predictors from purchasing histories, including:

- Purchase frequency and spending patterns
- Product category diversity
- Customer purchase history duration and recency
- Proportions of toy, baby-product, and pet-related purchases

Random forest feature importance was used to select the top 45 predictors for model comparison.

## Model Results

Five predictive models were compared using 5-fold cross-validation.

| Model | CV RMSE |
|---|---|
| Gradient Boosting (Tuned) | 1.0300 |
| Random Forest | 1.0323 |
| Gradient Boosting (Shallow) | 1.0323 |
| Ridge Regression | 1.0458 |
| Lasso Regression | 1.0463 |

The tuned Gradient Boosting model achieved the lowest reported cross-validation RMSE.

**Validation note:** Feature selection was performed before cross-validation, so the reported RMSE may be optimistic. A future improvement would repeat feature selection within each training fold.

## Key Findings

- Toy- and baby-related purchasing behavior showed useful predictive signals for household size.
- Tree-based models performed slightly better than the regularized linear models.
- Purchase history alone provided limited predictive accuracy, suggesting additional demographic or contextual features may improve results.

## Project Files

- `code_Guo_Chu.Rmd` — R Markdown analysis and model development
- `Guo_Chu_report.pdf` — Final project report with visualizations and interpretation

## Limitations

Household size was recorded on a scale of 1–4, with 4 representing four or more people. Predictions were evaluated using RMSE, and the final model's performance was limited by weak individual predictor relationships.

## Author

Guo On Chu  
University of California, Los Angeles (UCLA)  
Statistics & Data Science
