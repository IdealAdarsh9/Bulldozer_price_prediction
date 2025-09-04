# 🏗️ Bulldozer Price Prediction (Kaggle Blue Book for Bulldozers)

This project is based on the [Kaggle competition: Blue Book for Bulldozers](https://www.kaggle.com/c/bluebook-for-bulldozers).  
The goal is to predict the **sale price of bulldozers** sold at auctions, using historical data.

---

## 📌 Project Overview
- **Problem Type:** Regression  
- **Target Variable:** `SalePrice` (bulldozer auction sale price)  
- **Evaluation Metric:** RMSLE (Root Mean Squared Logarithmic Error)  
- **Dataset:** Contains equipment attributes, usage, and auction details.

We build an **end-to-end machine learning pipeline** that:
1. Preprocesses raw training & test data
2. Performs exploratory data analysis (EDA)
3. Trains a regression model (Random Forest Regressor as baseline, tuned later)
4. Generates predictions on the test dataset
5. Prepares a submission file for Kaggle

---

## 📂 Dataset
- **Train.csv** – training data with features + target
- **Valid.csv** – validation data for offline evaluation (optional split)
- **Test.csv** – test data (without target, for Kaggle submission)

---

## ⚙️ Workflow

### 1. Data Preprocessing
- Parse `saledate` into `year`, `month`, `dayofweek`, `dayofyear`
- Handle missing values
- Encode categorical features
- Drop unused/irrelevant columns
- Ensure train & test sets have the **same feature names and order**

### 2. Modeling
- Baseline: Random Forest Regressor
- Tuned model with hyperparameter optimization
- Evaluation using RMSLE, RMSE, R²

### 3. Prediction
- Apply preprocessing to **Test.csv**
- Align features with training (`model.feature_names_in_`)
- Predict bulldozer sale prices
- Save predictions to `submission.csv`

### 4. Submission
Final submission format:
```csv
SalesID,SalePrice
12242,15950.00
12243,31000.50
...
