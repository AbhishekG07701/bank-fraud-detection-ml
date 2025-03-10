# 💳 Bank Transaction Fraud Detection Using Machine Learning  

## 📌 Project Overview  

Financial fraud costs billions annually, making fraud detection a **critical challenge** in banking and finance. This project leverages **Machine Learning & Data Science** to identify fraudulent transactions.  

### **🔎 Key Features & Insights:**  
✔ **Exploratory Data Analysis (EDA):** Analyzed transaction behaviors, fraud patterns, and risk factors.  
✔ **Feature Engineering:** Created new variables such as transaction amount-to-balance ratio and fraud indicators.  
✔ **Model Comparison:** Evaluated multiple ML models to select the most effective fraud detector.  
✔ **Performance Optimization:** Applied cross-validation and data balancing techniques to improve accuracy.  

---

## 📂 **Dataset Information**  
- **Source:** [Fraud Detection Transactions Dataset](https://www.kaggle.com/datasets/samayashar/fraud-detection-transactions-dataset/data)
- **Columns:**  
  - `transaction_amount`: Amount involved in the transaction  
  - `transaction_method`: Payment method used  
  - `account_balance`: User’s account balance before the transaction  
  - `device_type`: Type of device used for the transaction  
  - `transaction_location`: Location from where the transaction took place  
  - `merchant_category`: Business type (Retail, Travel, Food, etc.)  
  - `ip_address_flag`: Whether the IP was flagged as suspicious  
  - `previous_fraudulent_activities`: Whether there was any previous fraudulent activity related with the account.
  - `daily_transaction_count`: Total transactions made by the user on the given day  
  - `avg_transaction_amount_7d`: Average transaction amount over the past 7 days  
  - `failed_transaction_count_7d`: Number of failed transactions in the past 7 days  
  - `card_type`: Type of bank card used (e.g., Visa, MasterCard)  
  - `transaction_distance`: Distance between transaction location and user's registered address  
  - `authentication_method`: The security method used to verify the transaction  
  - `is_weekend`: Whether the transaction occurred on a weekend  
  - `fraud_label`: **Target variable** (1 = Fraud, 0 = Genuine)  
  - `day_of_week`, `transaction_hour`, `transaction_month`, `transaction_min`: Time-based features  
  - `transaction_amount_to_balance_ratio`: Ratio of transaction amount to account balance  
  - `is_high_value_transaction`: Whether the transaction is classified as high value  
  - `card_age_years`: Age of the bank card in years  

---

## 🛠 **Data Preprocessing & Feature Engineering**  

### **1️⃣ Data Cleaning & Transformation**  
- Handled missing and duplicate values.  
- Encoded categorical features like `transaction_method`, `card_type`, and `authentication_method`.  
- Standardized numerical features for consistency.  

### **2️⃣ Feature Engineering**  
- **Transaction Amount-to-Balance Ratio:** Helps flag unusually high transactions.    
- **Time-Based Features:** Identifying fraud patterns by hour, day, and month.  

---

## 🤖 **Machine Learning Model Comparison**  

| Model                     | Accuracy | Precision | Recall | F1-Score | ROC-AUC |  TP   |  TN   |  FP   |  FN   | Avg Training CV Score | Avg Testing CV Score |
|---------------------------|----------|-----------|--------|----------|---------|-------|-------|-------|-------|-----------------------|----------------------|
| Logistic Regression       | 80.81%   | 67.03%    | 80.66% | 73.22%   | 90.17%  | 2623  | 5458  | 1290  | 629   | 90.21%                | 90.23%               |
| SGD Classifier            | 80.82%   | 67.08%    | 80.53% | 73.20%   | 90.17%  | 2619  | 5463  | 1285  | 633   | 90.21%                | 90.22%               |
| K-Nearest Neighbors (KNN) | 85.26%   | 72.57%    | 87.88% | 79.50%   | 92.88%  | 2858  | 5668  | 1080  | 394   | 95.89%                | 90.50%               |
| **Random Forest** 🏆      | **100%** | **100%**  | **100%**| **100%** | **100%** | **3252**  | **6748**  | **0**     | **0**     | **99.99%**                | **100%**                 |
| AdaBoost                  | 100%     | 100%      | 100%   | 100%     | 100%     | 3252  | 6748  | 0     | 0     | 99.99%                | 99.98%               |
| Gradient Boosting         | 100%     | 100%      | 100%   | 100%     | 100%     | 3252  | 6747  | 1     | 0     | 99.99%                | 99.97%               |
| XGBoost                   | 99.80%   | 99.63%    | 99.75% | 99.69%   | 99.99%   | 3244  | 6736  | 12    | 8     | 99.99%                | 100%                 |

---

## 🏆 **Preventing Overfitting & Ensuring Model Generalization**  
✔ **Stratified K-Fold Cross-Validation:** Ensured stability across different data splits.  
✔ **Feature Selection:** Retained only the most relevant variables.  
✔ **Data Balancing:** Used SMOTE to handle class imbalance in fraud detection.  

---

## 📌 **Project Structure**  
📂 `data/`: Contains the dataset file  
📜 `bank_transaction_fraud_detection`: Jupyter notebooks for analysis & visualization  
📜 `README.md`: Project details and documentation 