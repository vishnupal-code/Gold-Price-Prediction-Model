# 🪙 Gold Price Prediction using Machine Learning

This project aims to predict the closing price of gold using historical and market-based financial indicators. It covers the full machine learning pipeline from preprocessing to deployment using a web-based interface.

---

## 📌 Objective

- Predict daily **gold closing prices** using relevant financial indicators.
- Identify key features that influence gold price.
- Develop and evaluate machine learning models.
- Package and deploy the final model with a web app interface.

---

## 📂 Dataset

- **Source**: [yfinance](https://pypi.org/project/yfinance/), [FRED](https://fred.stlouisfed.org/)
- **Features**: 80+ including:
  - Gold market data (Open, High, Low, Close)
  - Stock indices (S&P 500, DJIA, etc.)
  - Oil and USD index prices
  - Other precious metals (Platinum, Palladium)
- **Target**: `Close` (Gold closing price)

---

## 🧼 Data Preprocessing

- Handled missing values and dropped irrelevant columns
- Converted date column to datetime format
- Removed outliers using the IQR method across all numeric features
- No scaling required for tree-based models

---

## 🏗️ Feature Engineering

- Created lag-based features:
  - `Close_Lag1`, `Close_Lag2`, `Close_MA3`
- Calculated feature importance using Random Forest
- Selected top 8 features for efficient modeling

---

## 🤖 Machine Learning Models Used

| Model               | MAE  | RMSE  | R² Score |
|---------------------|------|-------|----------|
| Linear Regression   | 6.22 | 6.66  | -1.06    |
| Random Forest       | 3.34 | 4.07  | 0.227    |
| Support Vector Regressor (SVR) | 3.35 | 4.12 | 0.209    |
| Random Forest (Cleaned + Lag Features) | 0.43 | 0.55 | **0.967** ✅ |

✅ Best model: **Random Forest** with cleaned data and lag-based features

---

## 🧪 Evaluation Metrics

- **MAE**: Mean Absolute Error – average error
- **RMSE**: Root Mean Squared Error – gives weight to large errors
- **R² Score**: Indicates how well the model explains the variance (closer to 1 is better)

---

## 🌐 Web App (Streamlit)

A responsive and interactive web interface to input features and get predictions.

### 🔢 Features:
- Manual input for 8 important features
- Auto-fetch capability (extendable)
- Real-time predictions using `.pkl` model

---

## 📦 Project Files

- `gold.csv`: Dataset
- `gold_model_selected.pkl`: Final trained model
- `selected_features.json`: Features used in model
- `Gold_Price_Prediction_TeamB_Final.pptx/pdf`: Final presentation
- `app.py`: Streamlit web app (if added)

---

## 👨‍💻 Author

**Vishnu Pal Singh**  
_MCA Student & Data Enthusiast_  
_📅 Project Completed: July 2025_

---

## 🚀 Getting Started

1. Clone the repository  
   ```bash
   git clone https://github.com/your-username/gold-price-prediction.git
   cd gold-price-prediction
````

2. Install dependencies

   ```bash
   pip install -r requirements.txt
   ```

3. Run the app

   ```bash
   streamlit run app.py
   ```

---

## 📈 Future Scope

* Try LSTM and GRU for time-series deep learning
* Use real-time API for auto feature fetching
* Add cloud-based deployment (e.g., AWS or Streamlit Cloud)

---

## 📬 Contact

For queries or feedback, feel free to reach out via GitHub or email.

```
