
# 🧮 Customer Lifetime Value (CLTV) Prediction

##  Overview

**Customer Lifetime Value (CLTV)** is a predictive metric that estimates the total revenue or profit a business can expect from a customer over the course of their relationship. Understanding CLTV helps companies identify high-value customers, make informed marketing decisions, and allocate acquisition budgets more efficiently.

This project demonstrates the calculation of CLTV using transaction data, followed by predictive modeling using machine learning techniques such as Random Forest, Gradient Boosting, and XGBoost.

---

##  Why CLTV Matters

CLTV allows businesses to:

* 📊 Identify their **most profitable customers**
* 🎯 Design **targeted marketing strategies**
* 💰 Optimize **customer acquisition cost (CAC)**
* 🔄 Segment and retain **high-value customer segments**
* 📈 Forecast **long-term business growth**

---

## 🧠 CLTV Formula

We use a basic formula to compute CLTV:

```
CLTV = ((Average Order Value × Purchase Frequency) / Churn Rate) × Profit Margin
```

---

## 🧪 CLTV Calculation – Step-by-Step

### Step 1: Data Preprocessing

* Clean and merge transaction data
* Remove entries with missing Customer IDs
* Create new columns like `TotalPrice = Quantity × Price`

### Step 2: Feature Calculation

1. **Average Order Value (AOV)**
   `AOV = Total Revenue / Total Number of Transactions`

2. **Purchase Frequency**
   `Purchase Frequency = Total Number of Orders / Total Number of Customers`

3. **Repeat Rate & Churn Rate**
   `Repeat Rate = Customers with >1 Transaction / Total Customers`
   `Churn Rate = 1 - Repeat Rate`

4. **Profit Margin**
   For simplicity, we assume a 5% margin:
   `Profit Margin = Total Spend per Customer × 0.05`

5. **CLTV**

   * `Customer Value = (AOV × Purchase Frequency) / Churn Rate`
   * `CLTV = Customer Value × Profit Margin`

---

## 🔍 Predictive Modeling

After calculating historic CLTV, we use machine learning to **predict future CLTV** for each customer.

* **Target (y)**: Total revenue (CLV) over the 2-year period
* **Features (X)**: Recency, Tenure, Frequency, Avg Order Value, and additional engineered features

### Models Used

* 🌲 Random Forest Regressor
* 🌐 XGBoost Regressor
* 📈 Gradient Boosting Regressor

Model performance is evaluated using:

* **Root Mean Squared Error (RMSE)**
* **R² Score**

---

## 📊 Results

* Achieved up to **82% R² Score** with Random Forest
* Improvements tested using:

  * Feature engineering (e.g., Revenue per Day)
  * Hyperparameter tuning
  * Model comparison

---

## ✅ Pros of CLTV Modeling

* Enhances customer segmentation
* Informs strategic budgeting and marketing
* Helps forecast long-term revenue
* Supports targeted retention efforts

---

## ⚠️ Limitations

* CLTV is a **tool**, not a strategy — success depends on how insights are used.
* Over-focusing on profitable customers may overlook untapped segments.
* Misuse or misinterpretation of CLTV models can lead to biased decisions.

---

## 📁 Dataset

The dataset used is from Kaggle:
[Online Retail Dataset – by Lakshmi N Pathi](https://www.kaggle.com/datasets/lakshmi25npathi/online-retail-dataset)

---

## 📂 Project Structure

```
├── data/
│   └── online_retail_II.xlsx
├── clv_modeling.ipynb
├── README.md
```

---

## 🔧 Future Improvements

* Use deep learning models for prediction
* Include customer demographics for better segmentation
* Deploy as a REST API for real-time prediction

