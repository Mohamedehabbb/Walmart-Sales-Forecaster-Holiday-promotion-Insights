# Walmart-Sales-Forecaster-Holiday-promotion-Insights
end to end data science project




🏪 Walmart Weekly Sales Forecasting
Business-Aware Time Series Modeling with Machine Learning
📌 Problem Statement

Retail demand forecasting is inherently complex due to:

Strong seasonal patterns

Promotional markdown effects

Sudden demand spikes during holidays

Variability across stores and departments

The objective of this project was to build a robust time series forecasting model capable of predicting weekly sales while aligning evaluation with real business priorities — particularly the critical impact of holiday periods.

🎯 Business Goal

Develop a forecasting system that:

Predicts weekly sales per store & department

Avoids temporal data leakage

Handles volatility during holidays

Uses a business-weighted evaluation metric

This project simulates a real-world retail forecasting scenario where accuracy during peak periods matters more than average stability.

🛠️ Methodology
1️⃣ Data Integration

Merged:

Historical sales

External economic indicators

Promotional markdown data

Store metadata

Ensured chronological sorting and proper time indexing to preserve time-series integrity.

2️⃣ Feature Engineering Strategy

Rather than relying solely on model complexity, emphasis was placed on temporal intelligence:

Temporal Features

Year, Month, Week, Quarter

Lag Features

Lag_1, Lag_4, Lag_12
To capture short- and mid-term momentum.

Rolling Statistics

4-week rolling mean
To smooth short-term volatility.

Business Signals

Total promotional markdown

Store type encoding

This feature set allowed the model to understand seasonality, demand persistence, and promotional effects.

🤖 Modeling Approach

Model: LightGBM Regressor

Validation: TimeSeriesSplit (5 folds)

Evaluation Metric: Weighted MAE

Holiday weeks were weighted 5× higher to reflect their strategic importance.

This ensured the model was optimized for business impact rather than purely statistical accuracy.

📊 Results

Mean Weighted MAE: 239

Standard Deviation: 92

Observations:

The model captures overall demand trends effectively.

Holiday periods introduce significant volatility and higher error dispersion.

Early folds show higher instability due to limited seasonal exposure.

The variance across folds highlights the importance of long-term seasonal features.

⚠️ Key Challenges & Solutions
1️⃣ Holiday Volatility

Problem:
Extreme sales spikes during holidays caused performance degradation.

Action Taken:

Applied weighted evaluation

Conducted Holiday vs Non-Holiday error analysis

Visualized prediction gaps during peak demand

Insight:
Holiday-aware feature engineering is essential in retail forecasting.

2️⃣ Temporal Instability

Problem:
First cross-validation fold showed significantly higher error.

Root Cause:

Limited historical exposure

Insufficient seasonal memory

Resolution:

Fold-level performance analysis

Measured variability (mean + std)

Identified need for yearly lag features (Lag_52)

3️⃣ Skewed Sales Distribution

Problem:
Sales distribution exhibited extreme outliers.

Approach:

Tested log transformation

Compared performance on original scale

Conducted residual distribution analysis

Learning:
Evaluation on original scale remains essential for business interpretability.

📈 Analytical Visualization

Implemented interactive visualizations using Plotly:

Fold-level performance trends

Residual distribution

Holiday vs Non-Holiday error comparison

Actual vs Predicted time series plots

These visuals were critical for diagnosing temporal drift and volatility patterns.

🧠 Key Learnings

This project reinforced several advanced data science principles:

Proper time-series validation prevents misleading optimism.

Feature engineering often contributes more than model complexity.

Business-weighted metrics can significantly change model assessment.

Volatility requires domain-aware features, not just tuning.

Visualization bridges the gap between ML output and business insight.

🚀 Future Enhancements

Introduce Lag_52 for yearly seasonality

Engineer holiday proximity features

Perform hyperparameter optimization

Apply SHAP for interpretability

Develop interactive store-level performance dashboard

Implement prediction intervals for uncertainty quantification

🏁 Final Takeaway

This project demonstrates a production-style forecasting pipeline that integrates:

Structured time-series feature engineering

Business-aligned evaluation

Cross-validation without leakage

Diagnostic performance analysis

Insight-driven improvement planning

It reflects not only modeling capability, but also structured analytical thinking and business awareness — key competencies for applied data science in real-world retail environments.
