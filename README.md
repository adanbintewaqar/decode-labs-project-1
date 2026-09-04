# Project 1: Advanced Exploratory Data Analysis (EDA) & Feature Engineering

## 📌 Project Overview

This project was completed as part of my **Data Science Internship at DecodeLabs** and represents my **first-ever real Data Science project**.

The goal of the project was to take raw e-commerce transactional data and transform it into a clean, structured, and analysis-ready dataset through a systematic data preprocessing and feature engineering workflow.

The project follows an **Input → Process → Output (IPO)** approach, covering data cleaning, outlier treatment, feature creation, categorical encoding, and data validation.

---

## 🎯 Objectives

The main objectives of this project were to:

- Identify and handle missing values appropriately
- Detect and mitigate extreme numerical outliers
- Perform efficient data transformations using Python
- Convert categorical variables into numerical representations
- Identify highly correlated features and address multicollinearity
- Create meaningful features from existing transactional data
- Validate the processed dataset
- Export a clean dataset for further analysis and machine learning

---

## 🔄 Project Workflow

**Raw Data → Data Cleaning → Outlier Treatment → Feature Engineering → Encoding → Correlation Analysis → Validation → Clean Dataset**

---

## 🧹 1. Data Cleaning

The raw dataset was examined for missing and inconsistent values.

For the `CouponCode` column, approximately **25.75% of values were missing**. Since a missing coupon code can represent an order where no coupon was used, these values were replaced with:

`NO_COUPON`

This preserved the information contained in the missing entries rather than unnecessarily removing those records.

---

## 📊 2. Outlier Detection & Mitigation

Extreme values in numerical columns can significantly affect statistical analysis and future machine learning models.

The **Interquartile Range (IQR)** method was used to identify potential outliers in:

- `Quantity`
- `UnitPrice`
- `ItemsInCart`
- `TotalPrice`

The IQR boundaries were calculated using:

- **Lower Bound:** Q1 − 1.5 × IQR
- **Upper Bound:** Q3 + 1.5 × IQR

Instead of removing affected rows, extreme values were capped using `numpy.clip()` to preserve the overall dataset size while reducing the influence of unusually large or small observations.

---

## ⚙️ 3. Feature Engineering

New features were created from the existing transactional information to make the dataset more informative.

### Features Created

| Feature | Description |
|---|---|
| `Has_Coupon` | Binary indicator showing whether a coupon was used |
| `Is_Weekend` | Indicates whether the transaction occurred on a weekend |
| `AvgPricePerCartItem` | Average transaction value per item in the cart |
| `QuantityToCartRatio` | Ratio of ordered quantity to total items in the cart |

These features provide additional information that may be useful for future analysis and predictive modeling.

---

## 🔢 4. Categorical Encoding

Machine learning algorithms generally require numerical inputs.

Categorical variables were therefore transformed using **One-Hot Encoding** with `pandas.get_dummies()`.

This converts categorical values into numerical indicator columns while avoiding the assumption of an artificial ranking between categories.

---

## 🔗 5. Correlation & Multicollinearity

Relationships between numerical features were examined to identify highly correlated variables.

Highly correlated features can introduce **multicollinearity**, which may make certain machine learning models harder to interpret.

The analysis was therefore used to identify redundant information and determine whether any features should be removed or retained.

---

## 🚀 6. Data Validation

The processed dataset was checked to ensure that the required transformations had been applied and that the resulting data was suitable for further analysis.

The final output was saved as a cleaned CSV dataset that can be used as input for subsequent data science and machine learning tasks.

---

## 🛠️ Technologies Used

- **Python**
- **Pandas**
- **NumPy**
- **Scikit-learn**
- **Pandera**
- **Google Colab**
- **Jupyter Notebook**

---

## 📁 Repository Structure

```text
decode-labs-project-1/
│
├── Project_1_Advanced_EDA.ipynb
├── Cleaned_Data_Analytics_Dataset.csv
└── README.md
