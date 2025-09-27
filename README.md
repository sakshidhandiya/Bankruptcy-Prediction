# Bankruptcy-Prediction
Predicting firm bankruptcy using logistic regression with class balancing and L1-regularization for actionable financial insights.
🚀 Project Overview

This project applies logistic regression to predict bankruptcy in firms based on financial ratios. The aim is to identify high-risk firms early and provide actionable insights for management, using advanced preprocessing, class balancing, and regularization techniques.

Domain: Financial Risk / Operations
Techniques: Logistic Regression, L1 Regularization, Class Balancing, VIF Analysis
Tools: Python (pandas, scikit-learn, numpy)
📊 Dataset

Features: Ratio1, Ratio2, …, Ratio10 (financial ratios), FYEAR

Target: Bankruptcy Status (0 = Not Bankrupt, 1 = Bankrupt)

Size: 535 records (imbalanced classes: 459 non-bankrupt, 76 bankrupt)

🛠 Methodology
1. Data Preprocessing

Removed duplicates and irrelevant identifiers (CUSTOMERID).

Checked for missing values and handled them.

Scaled and normalized ratios for model stability.

2. Train-Test Split

Stratified split: 70% training, 30% testing.

3. Multicollinearity Check

Calculated Variance Inflation Factor (VIF) for all ratios.

Moderate collinearity observed for Ratio3, Ratio9.

4. Baseline Logistic Regression

Built initial logistic regression model.

Metrics:

Accuracy: 87.6%

Recall (Bankrupt): 36.8% → model biased toward non-bankrupt class.

5. Handling Class Imbalance

Used class_weight='balanced' in logistic regression.

Metrics improved:

Recall (Bankrupt) → 84% ✅

Precision (Bankrupt) → 49%

Accuracy: 85.2%

6. L1 Regularization (Lasso)

Applied L1 penalty to reduce multicollinearity and highlight key ratios.

Key features identified: Ratio2, Ratio6, Ratio1 (increase risk) and Ratio10, Ratio3, Ratio7 (protective).

Metrics:

Accuracy: 78.1%

Recall (Bankrupt) → 79% ✅

Precision (Bankrupt) → 37%

📈 Results & Insights
Confusion Matrix (L1 + Balanced)
	Predicted Non-Bankrupt	Predicted Bankrupt
Actual Non-Bankrupt	359	100
Actual Bankrupt	16	60
Key Ratios Driving Bankruptcy
Ratio	Effect on Bankruptcy	Actionable Insight
Ratio2	↑ risk	Monitor high values; early intervention.
Ratio6	↑ risk	Track operational or liquidity signals.
Ratio1	Slight ↑ risk	Minor contributor; include in risk scoring.
Ratio10	↓ risk	Indicates stability; benchmark high-performing peers.
Ratio3	↓ risk	Encourage best practices linked to this ratio.
Ratio7	↓ risk	Incorporate in early-warning dashboards.
Interpretation

High recall prioritized: catching potential bankruptcies is critical.

Feature selection via L1 improves interpretability → stakeholders can focus on key ratios.

Actionable insights: Early-warning systems, operational monitoring, and best practice benchmarking.
