# Data Analysis  
**House Prices Prediction Project**

This project involves a predictive modeling task using a cleaned subset of the **Ames Housing dataset** (2,919 observations and 13 features). The primary goal is to identify key drivers of house sale prices and develop accurate regression models using core variables such as lot size, construction year, remodeling history, and basement size. The project includes data preparation, exploratory analysis, and evaluation of several machine learning models.

---

## 1. Dataset Overview

The original dataset has been reduced to 13 key variables. The final dataset contains no missing values after imputation and row-wise deletion. Categorical features were converted into numerical indicators using one-hot encoding.

### Feature Summary

| Variable | Type | Description |
|----------|------|-------------|
| `Id` | int | Unique identifier (excluded from modeling) |
| `MSSubClass` | int | Code for dwelling type |
| `MSZoning` | categorical | Zoning classification |
| `LotArea` | numeric | Lot size in square feet |
| `LotConfig` | categorical | Lot configuration |
| `BldgType` | categorical | Type of dwelling (e.g., single-family, duplex) |
| `OverallCond` | int | Overall condition of the property (1 = very poor, 10 = excellent) |
| `YearBuilt` | int | Year the house was originally built |
| `YearRemodAdd` | int | Year of last remodeling |
| `Exterior1st` | categorical | Exterior material type |
| `BsmtFinSF2` | numeric | Finished basement area (Type 2) |
| `TotalBsmtSF` | numeric | Total basement square footage |
| `SalePrice` | numeric | **Target variable** – house sale price |

*Total features after encoding: 29 columns (13 original, 16 dummy variables)*

---

## 2. Exploratory Data Analysis (EDA)

### 2.1 Correlation with Target (`SalePrice`)

| Feature | Pearson Correlation (ρ) |
|---------|--------------------------|
| `TotalBsmtSF` | **0.61** |
| `YearBuilt` | 0.52 |
| `YearRemodAdd` | 0.51 |
| `LotArea` | 0.26 |
| `BsmtFinSF2` | –0.01 |
| `MSSubClass` | –0.08 |
| `OverallCond` | –0.08 |
| `Id` | –0.02 |

**Key Insight**:  
Sale price is positively correlated with larger and newer homes. In contrast, subjective condition ratings (`OverallCond`) and finished basement area of type 2 (`BsmtFinSF2`) are weak predictors of price.

### 2.2 Feature Relationships

- `YearBuilt` and `YearRemodAdd` are strongly correlated (ρ = 0.61), indicating that homes built recently often receive renovations around the same time.
- `TotalBsmtSF` is moderately correlated with `YearBuilt` (ρ = 0.41), suggesting newer homes tend to have larger basements.
- No strong multicollinearity issues are observed among numeric predictors.

---

## 3. Predictive Modeling

Three machine learning models were implemented using the processed dataset. Preprocessing included scaling for models sensitive to feature magnitude.

### 3.1 Models Compared

| Model | Preprocessing | Mean Percentage Error (MPE) |
|-------|----------------|-----------------------------|
| **Linear Regression** | StandardScaler | **0.187** |
| **Support Vector Regression (SVR)** | StandardScaler | **0.187** |
| **Random Forest Regressor** | None | 0.194 |

**Observations:**

- Both linear regression and SVR achieved the lowest error (~18.7%), indicating strong performance on this limited feature set.
- Random Forest, while slightly less accurate, may perform better with more complex features or interactions.
- The relatively low MPE values suggest that simple models can be effective when key variables are well-engineered.

---

## 4. Key Insights & Business Recommendations

### 4.1 What drives sale price?

- **Basement size (`TotalBsmtSF`)** is the strongest driver of value.
- **Newer and recently remodeled homes** (`YearBuilt`, `YearRemodAdd`) consistently command higher prices.
- **Lot size** adds moderate value but has diminishing returns.
- Surprisingly, **overall condition scores** and **additional basement finish** (`BsmtFinSF2`) have negligible predictive power.

### 4.2 Modeling Recommendations

- The models benefit from **standardization** when using distance-based or linear methods.
- Future versions should explore **log-transformation** of `SalePrice` to address skewness and improve model fit.
- Including features like **neighborhood**, **garage size**, **number of rooms**, and **quality ratings** may significantly improve performance.
- Testing **advanced ensemble models** (XGBoost, LightGBM) with hyperparameter tuning is recommended.

---

## 5. Future Work

To enhance accuracy and predictive power, the following steps are suggested:

- **Feature expansion**: Integrate richer housing characteristics such as living area, number of bathrooms, fireplace presence, etc.
- **Temporal analysis**: Introduce time-of-sale or economic indicators (e.g., interest rates, seasonality).
- **Cross-validation**: Use k-fold CV or train/validation/test split for more robust generalization.
- **Price segmentation**: Explore clustering or classification-based segmentation to target specific price tiers.

---

## Conclusion

This analysis highlights how even a trimmed-down dataset with basic structural and temporal information can explain a large portion of sale price variance in residential housing. By using straightforward regression techniques and solid feature preprocessing, we achieve competitive predictive performance. Further improvements can be made by expanding the dataset, engineering domain-specific variables, and leveraging more sophisticated machine learning models.

---

*Prepared: July 14, 2025 (UTC+7)*

