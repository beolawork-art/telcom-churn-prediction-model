
# 📈 Telco Customer Churn Prediction: Strategic Retention Model

## 1. Executive Summary 📄

This project developed a machine learning model to proactively identify customers at high risk of churning from the telecom service. By successfully leveraging a **Weighted Logistic Regression** model, we can now flag customers for intervention, maximizing retention efforts and protecting revenue.

| Metric | Result | Interpretation for the Business |
| :--- | :--- | :--- |
| **Model Type** | Weighted Logistic Regression | Simple, stable, and highly interpretable. |
| **Overall Accuracy** | 75.16% | The model is correct 3 out of every 4 predictions. |
| **Churn Recall (Sensitivity)** | **83%** | **CRITICAL SUCCESS:** Our model catches **83%** of customers who are actually going to leave, minimizing revenue loss. |

---

## 2. Core Business Insights: Why Customers Churn 🔎

The model's coefficients revealed the strongest drivers of customer risk and stability:

### ⚠️ Top 3 Risk Factors (High Coefficient)
These features increase the probability of churn:
1.  **Internet Service: Fiber Optic:** The single highest risk factor, indicating severe underlying product or service quality issues.
2.  **Payment Method: Electronic Check:** High churn is correlated with this method, often associated with less stable, month-to-month customers.
3.  **Paperless Billing:** Customers receiving electronic bills show higher churn, suggesting a low commitment to the provider.

### ✅ Top 3 Stability Factors (High Negative Coefficient)
These features demonstrate high customer loyalty:
1.  **Contract: Two Year:** The single strongest guarantee of stability.
2.  **Online Security & Tech Support:** Customers who use value-added security or support are heavily invested and less likely to switch.
3.  **Internet Service: No:** These customers are highly stable, likely only requiring basic phone service.

---

## 3. Modeling Strategy and Optimization ⚙️

### A. Model Selection
The **Logistic Regression** model was chosen over the Random Forest model because it provided **clearer interpretability** of features and, critically, maintained higher performance (initial Accuracy $\text{82.04\%}$).

### B. The Optimization Success (Handling Imbalance)
Since only $\text{27\%}$ of customers churned (imbalanced data), the initial model missed too many high-risk customers ($\text{60\%}$ Recall). The final model was optimized using **Class Weighting** (`class_weight='balanced'`).

| Model | Churn Recall (Sensitivity) | Customers Missed (False Negatives) |
| :--- | :---: | :---: |
| **Initial Model** | 60% | 149 |
| **Final Weighted Model** | **83%** | **63** |

This strategic trade-off ensured the final model is prioritized for **maximum revenue protection**.

---

## 4. Key Recommendations for Stakeholders 🚀

Based on the model's findings, the following actions are recommended:

1.  **Fiber Optic Audit:** Initiate an immediate quality-of-service audit for the Fiber Optic product line to address the primary churn driver.
2.  **Contract Upgrades:** Target month-to-month customers with high-value offers to incentivize switching to one- or two-year contracts, leveraging the strongest stability factor.
3.  **Future Work (XGBoost):** To catch the remaining 17% of missed customers, the next phase will involve implementing the advanced **XGBoost** model to increase the Churn Recall beyond 85% further.

---
```
