![Python](https://img.shields.io/badge/Python-3.10+-blue)
![Machine Learning](https://img.shields.io/badge/Machine_Learning-Random_Forest-green)
![Analytics](https://img.shields.io/badge/Analytics-RFM-orange)
![Scikit Learn](https://img.shields.io/badge/Framework-Scikit_Learn-red)
![Customer Intelligence](https://img.shields.io/badge/Domain-Customer_Intelligence-purple)
![Status](https://img.shields.io/badge/Status-Completed-success)
# 📈 Customer Risk Intelligence Framework

A machine learning-driven customer analytics platform that predicts customer churn, quantifies customer value, estimates revenue at risk, and prioritizes retention actions based on business impact.

Built using **RFM Analysis**, **Customer Value Scoring**, and **Random Forest Classification** on real-world retail transaction data.

---

## 📌 Overview

Customer churn is one of the most significant challenges faced by subscription businesses, e-commerce platforms, retailers, and service providers.

While many churn prediction systems identify customers likely to leave, they often fail to answer a critical business question:

> Which customers should be prioritized for retention?

This project introduces a Customer Risk Intelligence Framework that combines:

* Customer behavioral analysis
* Customer Value Scoring (CVS)
* Churn prediction
* Revenue-at-risk estimation
* Risk-value segmentation

to enable data-driven retention strategies.

---

## 🎯 Business Problem

Traditional churn models focus solely on prediction accuracy.

However, losing a customer who spends ₹500 annually is fundamentally different from losing one who spends ₹50,000 annually.

Organizations need to know:

* Who is likely to churn?
* How valuable is that customer?
* What revenue is at risk?
* Which customers deserve immediate intervention?

This project addresses all four questions.

---

# 🚀 Key Contributions

✅ Customer behavior modeling using RFM analysis

✅ Customer Value Score (CVS) generation

✅ Churn prediction using Random Forest

✅ Revenue-at-risk estimation

✅ Risk–Value customer segmentation

✅ Actionable retention prioritization

---

# 🏗️ System Architecture

```text
                    Transaction Data
                            │
                            ▼
                Data Cleaning & Validation
                            │
                            ▼
                     RFM Analysis
          (Recency, Frequency, Monetary)
                            │
                            ▼
                Customer Value Scoring
                            │
                            ▼
                Churn Label Generation
                            │
                            ▼
              Random Forest Classifier
                            │
                            ▼
                  Churn Probability
                            │
                            ▼
             Risk–Value Segmentation
                            │
                            ▼
                 Revenue at Risk
                            │
                            ▼
              Retention Prioritization
```

---

# 📂 Dataset

The project uses the Online Retail transactional dataset containing:

* Invoice information
* Purchase timestamps
* Product details
* Customer IDs
* Quantity purchased
* Product prices

The dataset spans multiple years of customer purchasing activity.

---

# 🔍 Data Preprocessing

The following cleaning operations were performed:

### Missing Value Handling

Removed:

* Missing Customer IDs
* Missing Product Descriptions

### Cancellation Removal

Orders beginning with:

```python
Invoice.startswith("C")
```

were removed to exclude cancelled transactions.

### Invalid Transaction Removal

Filtered:

```python
Quantity > 0
Price > 0
```

to eliminate returns and invalid purchases.

### Datetime Processing

Invoice timestamps were converted into:

```python
datetime
```

format to support behavioral analysis.

---

# 📊 Feature Engineering

## Total Purchase Value

For every transaction:

```python
Total Purchase = Quantity × Price
```

This metric captures the monetary contribution of each transaction.

---

# 🧠 RFM Analysis

Customer behavior was modeled using the industry-standard RFM framework.

## Recency (R)

How recently the customer made a purchase.

Lower values indicate more active customers.

---

## Frequency (F)

Number of unique transactions completed by the customer.

Higher values indicate stronger engagement.

---

## Monetary Value (M)

Total spending by the customer.

Higher values indicate greater business value.

---

# 📈 Customer Value Score (CVS)

To move beyond churn prediction, a Customer Value Score was created.

The score combines:

* Purchase frequency
* Spending behavior
* Customer engagement

This allows retention decisions to be based on business impact rather than prediction alone.

---

# 🤖 Machine Learning Model

## Model Selected

Random Forest Classifier

Reasons:

* Handles nonlinear customer behavior
* Resistant to overfitting
* Provides feature importance
* Works effectively with tabular retail datasets

---

## Input Features

The model was trained using:

```python
Frequency
Monetary Value
Average Order Value
```

These features capture customer engagement and purchasing strength.

---

## Churn Target Definition

Customers were labeled as churned based on inactivity and purchasing behavior patterns.

This avoids relying on future information and reduces data leakage.

---

# 📉 Model Performance

## Accuracy

Approximately:

```text
70%
```

---

## ROC-AUC

Approximately:

```text
0.73
```

The ROC-AUC score indicates that the model can effectively distinguish between churning and non-churning customers.

---

## Churn Recall

Approximately:

```text
74%
```

Meaning the model correctly identifies most customers at risk of leaving.

---

# 📊 Feature Importance Analysis

The Random Forest model was analyzed to understand the primary drivers of churn.

Key predictors included:

### Monetary Value

Customers with lower spending patterns showed higher churn probability.

---

### Frequency

Less engaged customers demonstrated significantly greater churn risk.

---

### Average Order Value

Purchasing intensity contributed to retention likelihood.

---

# 🔥 Revenue-at-Risk Framework

One of the most important business outcomes of the project is identifying:

> Revenue that may be lost if high-risk customers churn.

Instead of treating every churn equally, the framework estimates:

```text
Churn Risk × Customer Value
```

to prioritize intervention efforts.

---

# 🎯 Risk–Value Segmentation

Customers are segmented into strategic categories.

## High Value + High Risk

🚨 Immediate retention required

Potential revenue loss is significant.

---

## High Value + Low Risk

⭐ Loyalty and relationship programs

Maintain engagement.

---

## Low Value + High Risk

⚠ Cost-sensitive retention campaigns

Selective intervention.

---

## Low Value + Low Risk

✅ Minimal monitoring required

---

# 📈 Business Impact

The framework enables organizations to:

* Reduce customer attrition
* Prioritize retention spending
* Improve customer lifetime value
* Protect recurring revenue streams
* Allocate marketing resources effectively

---

# ⚙️ Tech Stack

## Programming

* Python

## Data Analysis

* Pandas
* NumPy

## Visualization

* Matplotlib
* Seaborn

## Machine Learning

* Scikit-Learn

## Modeling

* Random Forest Classifier

---

# 📦 Installation

Clone the repository:

```bash
git clone https://github.com/yourusername/customer-risk-intelligence.git

cd customer-risk-intelligence
```

Install dependencies:

```bash
pip install -r requirements.txt
```

---

# 📄 requirements.txt

```text
pandas
numpy
matplotlib
seaborn
scikit-learn
openpyxl
```

---

# ▶️ Running the Project

Launch Jupyter Notebook:

```bash
jupyter notebook
```

Open:

```text
Customer_Risk_Intelligence.ipynb
```

Run all cells sequentially.

---

# 📊 Example Business Questions Answered

### Which customers are most likely to churn?

Predicted using Random Forest Classification.

---

### Which customers generate the highest revenue?

Identified using Customer Value Score.

---

### How much revenue is at risk?

Estimated through risk-value analysis.

---

### Which customers should retention teams contact first?

Determined through risk–value segmentation.

---

# 🔮 Future Improvements

## Gradient Boosting Models

* XGBoost
* LightGBM
* CatBoost

for improved predictive performance.

---

## Explainable AI

Integrate:

* SHAP
* LIME

to improve model transparency.

---

## Real-Time Customer Monitoring

Deploy the model as:

* REST API
* Dashboard
* CRM Integration

---

## Deep Learning Extensions

Explore:

* Temporal customer behavior modeling
* Sequential purchase forecasting
* Customer lifetime value prediction

---

# 📚 Key Learnings

This project demonstrates:

* Customer Analytics
* Churn Prediction
* RFM Analysis
* Customer Segmentation
* Revenue Intelligence
* Feature Engineering
* Random Forest Modeling
* Business-Focused Machine Learning

---

# 👨‍💻 Author

**Soham Dutta**

Machine Learning Engineer | Data Analytics | Customer Intelligence | Predictive Modeling

If you found this project useful, consider giving it a ⭐ on GitHub.
