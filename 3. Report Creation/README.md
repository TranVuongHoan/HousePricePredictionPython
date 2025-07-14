# House Prices Prediction Report  
**Insights Presentation**

This report offers an in-depth overview of the key factors influencing residential property sale prices in Ames, Iowa. The interactive report allows users to explore housing market patterns, price drivers, and model predictions across different features. It is designed to support data-driven real estate strategies by surfacing trends, patterns, and actionable insights.

📊 **Link to the Interactive Power BI Report**: [Report]  

📌 **Disclaimer**: This report was created with US-format settings (EN-US). If the numeric values appear inconsistent, please ensure your browser's regional settings match this format.

---

## Overview

This page provides a comprehensive summary of the housing data and model predictions:

- **Key Metrics**: Shows average sale price, total properties analyzed, feature completeness, and overall model error metrics (MPE, R²). These KPIs give a snapshot of data quality and predictive performance.
- **Sale Price Distribution**: Histogram showing price ranges across the dataset to highlight pricing clusters and potential outliers.
- **Sale Price by Year Built/Remodeled**: Highlights the value impact of property age and renovations.
- **Average Price by Building Type and Zoning**: Provides insights into how property type and zoning classification influence price.
- **Basement Size vs Sale Price**: Visual correlation of `TotalBsmtSF` with sale prices, showing how basement area drives property value.

---

## Structural Features

This section highlights how the physical characteristics of a home affect its market value:

- **Lot Area vs Sale Price**: Scatter plot showing the effect of land size on sale price, identifying diminishing marginal returns after certain thresholds.
- **Basement Area Analysis**: Visualizes relationships between `BsmtFinSF2`, `TotalBsmtSF`, and price, helping to identify under- or over-utilized basement space.
- **Exterior Material and Condition**: Box plots that compare average prices across different `Exterior1st` materials and `OverallCond` scores.
- **Renovation Impact**: Bar chart showing how recent remodeling boosts value, especially for older homes.

---

## Market Segmentation

This page breaks down performance by market-related features such as zoning and lot configuration:

- **Zoning Success Factors**: Compare average sale prices by `MSZoning` category to determine the most valuable zoning classes.
- **Lot Configuration Analysis**: View the influence of different lot layouts (`LotConfig`) on property price and marketability.
- **Building Type Distribution**: Identify how common each building type (`BldgType`) is and how it relates to price tiers.

---

## Model Evaluation

This page presents an overview of the model performance:

- **Model Comparison (Linear, SVR, Random Forest)**:
  - Mean Percentage Error (MPE)
  - R² Score
  - Interpretation of strengths and weaknesses
- **Prediction vs Actual Scatter Plot**: Measures how well each model fits the true `SalePrice`, highlighting accuracy and outliers.
- **Residual Distribution**: Shows where and how predictions deviate from actual values.
- **Feature Importance (Random Forest)**: Ranks variables by predictive power (e.g., `TotalBsmtSF`, `YearBuilt`, `YearRemodAdd`).

---

## Recommendations

This section offers data-driven guidance for homebuyers, sellers, and real estate professionals:

- **For Sellers**:  
  - Prioritize finishing basements and recent renovations for maximum ROI.  
  - Newer homes can command a premium—highlight construction date in listings.  

- **For Buyers**:  
  - Consider undervalued homes with large basements or recent updates.  
  - Use zoning and lot configuration data to assess long-term investment potential.  

- **For Developers & Appraisers**:  
  - Track neighborhood-level features to better assess fair market value.  
  - Include more granular condition/quality metrics for valuation accuracy.

---

## Actionable Insights

- **Basement Size Is Key**: Total basement area is the single strongest predictor of sale price in this dataset.  
- **New Builds and Remodels Sell for More**: Recency of construction and updates have a large and consistent positive effect.  
- **Simple Condition Scores Are Weak Predictors**: `OverallCond` has minimal correlation with price — suggesting a need for better quality indicators.  
- **Even Simple Models Perform Well**: Linear regression and support vector models achieved sub-19% MPE with just 13 variables.  

---

*Report created based on the Jupyter notebook (`house.ipynb`) executed on July 14, 2025.*

