# Bankruptcy-Prediction
Predicting firm bankruptcy using logistic regression with class balancing and L1-regularization for actionable financial insights.
🚀 Project Overview

This project applies logistic regression to predict bankruptcy in firms based on financial ratios. The aim is to identify high-risk firms early and provide actionable insights for management, using advanced preprocessing, class balancing, and regularization techniques.

Domain: Financial Risk / Operations

Techniques: Logistic Regression, L1 Regularization, Class Balancing, VIF(Variance Inflation Factor) Analysis to detect multicolinearity

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
Confusion Matrix (L1 + Balanced):

	Actual Non-Bankrupt predicted as Non-Bankrupt: 359 → correctly identified.

	Actual Non-Bankrupt predicted as Bankrupt: 100 → false positives.

	Actual Bankrupt predicted as Non-Bankrupt: 16 → false negatives (missed bankruptcies).

	Actual Bankrupt predicted as Bankrupt: 60 → correctly identified bankrupt firms.

Key Ratios Driving Bankruptcy:

	Ratio2: Increases bankruptcy risk → monitor high values and take early interventions.

	Ratio6: Increases bankruptcy risk → track operational or liquidity signals closely.

	Ratio1: Slightly increases risk → minor contributor; include in risk scoring models.

	Ratio10: Decreases bankruptcy risk → indicates financial stability; benchmark against high-performing peers.

	Ratio3: Decreases bankruptcy risk → encourage best practices linked to this ratio.

	Ratio7: Decreases bankruptcy risk → incorporate into early-warning dashboards for monitoring.

Interpretation:

	High recall prioritized: catching potential bankruptcies is critical.

	Feature selection via L1 improves interpretability → stakeholders can focus on key ratios.

Actionable Recommendations:

	Integrate these key ratios into early warning dashboards.

	Prioritize high recall detection: catching potential bankrupt firms early is more critical than occasional false positives.

	Review policies, operational metrics, or financial controls that influence Ratio2 and Ratio6.

	Benchmark best practices from firms with high Ratio10, Ratio3, Ratio7.
