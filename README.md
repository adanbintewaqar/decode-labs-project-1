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
