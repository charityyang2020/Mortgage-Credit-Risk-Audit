# Mortgage-Credit-Risk-Audit
A robust predictive model and macroeconomic sensitivity audit for mortgage risk using Python.
This project develops a robust analytical pipeline—encompassing exploratory data analysis (EDA), strategic feature engineering, and predictive modeling—utilizing the Realistic Loan Approval Dataset (US & Canada). The dataset contains 50,000 records across 18 predictors and a single target variable, loan_status. A structural audit confirmed 100% data integrity with no missing values or duplicate records.

During the preprocessing phase, frequency distributions and quantitative visualizations are leveraged to identify critical risk drivers. Outlier detection is performed on key leverage metrics, including Debt-to-Income (DTI), Loan-to-Income, and Payment-to-Income ratios. To enhance the model's predictive signal, three domain-driven features were engineered:
Severe_delinquency_flag: It represents 3+ delinquencies, which is a critical risk threshold for the lender, and they will 100% reject the loan application.
Has_derogatory_marks: It is used to flag those applicants whose derogatory_marks is 1 or more.
High_payment_burden: When the payment_to_income_ratio is above 40%, it is regarded as high payment burden.

During the predictive modeling phase, I utilizes a Logistic Regression model trained on a 60/20/20 (Train/Validation/Test) split. Through Information Value (IV) analysis and Variance Inflation Factor (VIF) testing, the model is optimized to six core features. Credit Score and Years Employed emerged as the strongest positive predictors. Conversely, the Severe Delinquency Flag exhibited the largest negative magnitude, followed by DTI. Factors such as High Payment Burden and Has Derogatory Marks provide statistically significant incremental risk signals.

The model demonstrated exceptional stability, achieving a consistent 80% accuracy and a balanced F1-score (within 1% variance) across both validation and test datasets. An AUC of 0.88 indicates an 88% probability that the model correctly distinguishes between low-risk and high-risk applicants, proving the model has captured the underlying economic laws of the population rather than simply memorizing the training subset.

Sensitivity analysis was conducted to simulate two stress scenarios: a 10% and 20% increase in average DTI due to inflationary pressures or interest rate hikes. The results confirm that the model is economically aware; as debt burdens rise, the model proactively tightens lending standards to safeguard institutional capital. The project concludes with data-driven policy recommendations for risk-based underwriting.
