# Customer Return Prediction & Analysis

This project focuses on analyzing and predicting product returns in an e-commerce environment. It combines statistical insights, machine learning models, and business intelligence to help retailers reduce return rates and optimize strategies.

---

## Project Goals

- Understand which customers and products are most likely to return orders
- Analyze return reasons and financial impact
- Build a machine learning model to predict returns
- Visualize patterns using Power BI dashboards

---

## Dataset Overview

- `customers.xlsx`: Customer info (age, country, loyalty segment)
- `sales.xlsx`: Order details including price, discount, quantity, return status

After merging, the dataset includes features like:
- Customer demographics and segments
- Product category, price, shipping cost
- Discounts, ad spend, return reasons
- Order date (converted to day, month, year)

---

## Descriptive Analytics

Performed visual and statistical analysis to answer:
- Which products/categories have high return rates?
- How do country, age, and loyalty segment affect returns?
- What are the financial losses from returns?
- Do marketing channels, discounts, or ad spend influence returns?

Visual tools used:
- Barplots, Boxplots, Violinplots
- Heatmaps, Pairplots, Pivot tables

---

## Diagnostic Analytics

Applied statistical tests to validate findings:

- `t-test`, `Mann-Whitney`: compare numerical features (price, age) by return status
- `ANOVA`, `Kruskal`: compare return rates across countries
- `Chi-square`: evaluate dependency between categories and return rate
- `Pearson`, `Spearman`: check correlation with `returned`

---

## Class Imbalance Handling

Returns (class 1) are much fewer than non-returns (class 0).

Solution: Applied **SMOTE** to oversample the minority class before training to avoid bias in the model.

---

## Predictive Modeling

**Target variable**: `returned` (0 = not returned, 1 = returned)

### Models:
- BaggingClassifier (with DecisionTree)
- RandomForestClassifier (with GridSearchCV)
- **XGBoostClassifier (Best Performance)**

# Pipeline:
SMOTE → Model → Predictions


Evaluation Metrics:
Accuracy

Precision, Recall

F1 Score

Confusion Matrix

Power BI Dashboards
Created dashboards for business users to monitor:

Return trends by product, customer segment, country

Return reasons and seasonal patterns

Financial losses and marketing influences

Dashboards available in the /PowerBI/ folder.

Business Use Case
This solution helps:
Identify high-risk orders and customers
Reduce return rates and lost revenue
Improve marketing and product quality strategies
Integrate predictive insights into e-commerce platforms

How to Run
Clone this repo

Install dependencies
Run the Python script for training and predictions

Explore Power BI dashboards (in .pbix file)
Files Included
customers.xlsx, sales.xlsx – raw data
classified_data.xlsx – final predictions
best_model_xgboost.pkl – trained model
PowerBI/ – dashboards and visuals
return_prediction.py – full pipeline script




