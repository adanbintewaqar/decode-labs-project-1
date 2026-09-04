# decode-labs-project-1
# Project 1: Advanced EDA & Feature Engineering Pipeline

## Project Overview
This project processes raw e-commerce order data using an Input-Process-Output (IPO) data architecture. It cleans missing data, neutralizes numerical outliers, engineers domain-specific features, and prepares real-valued vectors for Machine Learning estimators.

## Key Pipeline Transformations
1. **Missing Data Imputation**:
   - Imputed missing values in `CouponCode` (25.75% missingness) with a categorical fallback (`NO_COUPON`).
2. **Outlier Mitigation**:
   - Applied Interquartile Range (IQR) boundary calculations ($Q_1 - 1.5 \times \text{IQR}$ and $Q_3 + 1.5 \times \text{IQR}$) to numerical features (`Quantity`, `UnitPrice`, `ItemsInCart`, `TotalPrice`).
   - Capped extreme values using `numpy.clip()` to preserve row volume.
3. **Feature Engineering**:
   - `Has_Coupon`: Binary feature indicating whether a promo code was redeemed.
   - `Is_Weekend`: Binary flag derived from transaction timestamp.
   - `AvgPricePerCartItem`: Derived numerical ratio of total spending divided by item volume.
   - `QuantityToCartRatio`: Ratio of ordered items relative to overall cart items.
4. **Encoding**:
   - Converted categorical features into orthogonal vectors using One-Hot Encoding (`pd.get_dummies`).

## Project Structure
- `Project_1_Advanced_EDA.ipynb`: Complete Google Colab notebook containing executable code.
- `Cleaned_Data_Analytics_Dataset.csv`: Exported production-ready dataset.

# Data Analytics & Machine Learning Pipeline

## Project Overview
This repository contains an end-to-end data analytics and predictive modeling pipeline built in Python using Google Colab. The project processes raw e-commerce transaction data, cleans missing values, neutralizes outliers, engineers features, and trains machine learning models to predict order prices.

---

## Key Pipeline Stages

### 1. Advanced EDA & Feature Engineering (Project 1)
- **Missing Value Imputation**: Imputed missing values in `CouponCode` (25.75% missingness) using a categorical fallback (`NO_COUPON`).
- **Outlier Mitigation**: Calculated IQR boundaries ($Q_1 - 1.5 \times \text{IQR}$ and $Q_3 + 1.5 \times \text{IQR}$) and capped extreme numerical values (`Quantity`, `UnitPrice`, `ItemsInCart`, `TotalPrice`) using `numpy.clip()`.
- **Feature Engineering**: Created 4 domain-specific features:
  - `Has_Coupon`: Binary indicator for promo code usage.
  - `Is_Weekend`: Binary flag extracted from transaction dates.
  - `AvgPricePerCartItem`: Ratio of total order price to items in cart.
  - `QuantityToCartRatio`: Proportion of ordered product quantity relative to overall cart size.
- **Categorical Encoding**: One-Hot Encoded non-ordinal categories using `pd.get_dummies()`.

### 2. Predictive Machine Learning (Project 2)
- **Problem Type**: Supervised Regression (Target: `TotalPrice`).
- **Data Splitting**: 80% Train Set / 20% Test Set using `train_test_split`.
- **Model**: Linear Regression.
- **Performance Evaluation**: Evaluated using R² Score and Mean Absolute Error (MAE).

---

## File Structure
- `Project_1_Advanced_EDA.ipynb`: Complete Google Colab notebook with clean, executable code for both stages.
- `Cleaned_Data_Analytics_Dataset.csv`: Final preprocessed and engineered dataset ready for analysis.

### 3. Supervised Classification (Project 3)
- **Problem Type**: Multi-Class Classification (Target: `OrderStatus`).
- **Algorithm**: Random Forest Classifier (`n_estimators=100`).
- **Data Splitting**: Stratified 80/20 Train-Test split.
- **Performance Evaluation**: Accuracy, Precision, Recall, F1-Score, and Confusion Matrix metrics.
# End-to-End Data Analytics & Machine Learning Pipeline

## Project Overview
This repository contains a full end-to-end data processing, predictive regression, supervised classification, and model interpretability pipeline built using Python and Google Colab for DecodeLabs.

---

## Pipeline Summary

### Module 1: Advanced EDA & Feature Engineering
- Imputed missing `CouponCode` values with `NO_COUPON`.
- Capped numerical outliers (`Quantity`, `UnitPrice`, `ItemsInCart`, `TotalPrice`) using IQR boundaries.
- Engineered features: `Has_Coupon`, `Is_Weekend`, `AvgPricePerCartItem`, `QuantityToCartRatio`.
- One-Hot Encoded categorical attributes.

### Module 2: Predictive Regression Modeling
- **Task**: Continuous prediction of `TotalPrice`.
- **Model**: Linear Regression.
- **Metrics**: R² Score and Mean Absolute Error (MAE).

### Module 3: Supervised Multi-Class Classification
- **Task**: Predict transaction `OrderStatus` (Delivered, Pending, Cancelled, Returned, Shipped).
- **Model**: Random Forest Classifier (`n_estimators=100`).
- **Metrics**: Accuracy, Precision, Recall, and F1-Score.

### Module 4: Model Interpretability & Feature Analysis
- Extracted Gini importance metrics from tree-based estimators.
- Quantified domain feature contributions to model decision boundaries.

---

## File Structure
- `Project_1_Advanced_EDA.ipynb`: Complete, fully-documented Google Colab notebook.
- `Cleaned_Data_Analytics_Dataset.csv`: Cleaned output dataset.

# End-to-End E-Commerce Data Analytics & Machine Learning Suite

## Project Overview
An end-to-end data analytics and predictive modeling suite built for DecodeLabs using Python and Google Colab. The project handles data ingestion, outlier treatment, feature engineering, regression modeling, multi-class classification, hyperparameter optimization, model interpretability, and interactive web application deployment.

---

## Pipeline Architecture

| Module | Objective | Technique / Algorithm | Primary Metric |
| :--- | :--- | :--- | :--- |
| **1. Data Preprocessing** | Imputation & Outlier Mitigation | Median/Fallback Imputation, IQR Clipping | Clean Data Matrix |
| **2. Feature Engineering** | Domain Feature Creation | Ratio & Binary Date Transformations | 4 Engineered Columns |
| **3. Regression** | Continuous Price Prediction | Linear Regression | R² Score / MAE |
| **4. Classification** | Order Status Categorization | Multi-Class Random Forest | Classification Accuracy |
| **5. Interpretability** | Feature Impact Analysis | Gini Importance Extraction | Feature Ranking |
| **6. Optimization** | Model Tuning & Selection | GridSearchCV vs. Logistic Regression | Optimized Hyperparameters |
| **7. Deployment** | Interactive Web Demo | Gradio Interface Integration | Real-time Inference App |

---

## Executive Key Findings
1. **Predictive Accuracy**: Tree-based estimators provided robust multi-class order tracking predictions across fulfillment states.
2. **Core Price Drivers**: Features such as `Quantity`, `UnitPrice`, and `AvgPricePerCartItem` captured over 70% of variation in total transaction amounts.
3. **Operational Value**: Live input testing via Gradio demonstrates real-time decisioning capability for e-commerce order workflows.
 <img width="1879" height="815" alt="image" src="https://github.com/user-attachments/assets/282da2d4-2d67-4a8e-8675-d6b6822728de" />
