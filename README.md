# 🏪 Store Sales Forecasting



## 📌 Project Overview

This project builds a **Sales Forecasting System** using historical store sales data. The model predicts future sales across **54 stores** and **33 product categories** using Machine Learning — helping businesses plan inventory, manage cash flow, and avoid overstocking or losses.

---

## 📊 Dataset

**Store Sales — Time Series Forecasting**

| Detail | Info |
|--------|------|
| Source | [Kaggle](https://www.kaggle.com/competitions/store-sales-time-series-forecasting) |
| Records | 3,000,888 rows |
| Period | January 2013 — August 2017 |
| Stores | 54 stores |
| Product Categories | 33 families |

---

## 🗂️ Project Structure

```
store-sales-forecasting/
│
├── notebooks/
│   └── sales_forecasting.ipynb   ← Full ML pipeline in one notebook
│
├── data/
│   ├── train.csv                 ← Raw training dataset
│   ├── test.csv                  ← Test dataset
│   ├── stores.csv                ← Store metadata
│   ├── oil.csv                   ← Daily oil prices
│   └── holidays_events.csv       ← National holidays calendar
│
├── outputs/
│   └── sales_forecasting_results.png  ← 6 business-ready charts
│
├── submission.csv                ← Model predictions
├── requirements.txt              ← Python dependencies
├── .gitignore
└── README.md
```

---

## ⚙️ How to Run

### 1. Clone the repository
```bash
git clone https://github.com/vhogod/FUTURE_ML_01.git
cd FUTURE_ML_01
```

### 2. Install dependencies
```bash
conda activate base
pip install pandas numpy scikit-learn matplotlib seaborn
```

### 3. Add data files
Download the dataset from [Kaggle](https://www.kaggle.com/competitions/store-sales-time-series-forecasting) and place the CSV files inside the `data/` folder.

### 4. Open the notebook
```bash
jupyter notebook notebooks/sales_forecasting.ipynb
```

Run all cells from top to bottom — all outputs are generated automatically.

---

## 🔧 What the Notebook Does

| Section | Description |
|---------|-------------|
| **Data Loading** | Loads 5 CSV files into pandas DataFrames |
| **Data Cleaning** | Fills oil price gaps, parses dates, fixes missing values |
| **Merging** | Combines store info, oil prices, and holiday flags |
| **Feature Engineering** | Creates 20 time-based and seasonal features |
| **Model Training** | Trains Linear Regression + Gradient Boosting |
| **Evaluation** | Computes MAE, RMSE, R² on validation set |
| **Visualization** | Saves 6 business-ready charts |
| **Predictions** | Generates submission.csv for test set |

---

## 🧠 Features Created

| Feature | Description |
|---------|-------------|
| `year`, `month`, `quarter` | Time-based breakdown |
| `day_of_week`, `week` | Weekly patterns |
| `is_weekend` | Weekend sales flag |
| `is_holiday` | National holiday flag |
| `days_since_start` | Captures overall sales trend |
| `family_enc` | Product category as number |
| `city_enc`, `state_enc`, `type_enc` | Store location encoded |
| `oil_price` | Ecuador oil price (economy indicator) |
| `onpromotion` | Number of items on promotion |

---

## 📈 Model Results

| Model | MAE | RMSE | R² |
|-------|-----|------|----|
| Linear Regression (Baseline) | 469.29 | 1075.83 | 0.37 |
| **Gradient Boosting (Main)** | **274.67** | **728.35** | **0.71** |

**Gradient Boosting is the best model with R² = 0.71** — meaning it explains 71% of all sales variation across 54 stores and 33 product families.

---

## 📉 Visualizations

| Chart | What It Shows |
|-------|---------------|
| `Actual vs Predicted` | How closely the model tracks real sales |
| `MAE Comparison` | Error comparison between models |
| `R² Comparison` | Accuracy comparison between models |
| `Feature Importances` | Which factors influence sales the most |
| `Monthly Sales Trend` | Sales growth from 2013 to 2017 |
| `Sales by Day of Week` | Weekly seasonality pattern |

---

## 💡 Business Insights

- **Product family** and **promotions** are the strongest predictors of sales
- Sales follow clear **weekly patterns** — weekends consistently outperform weekdays
- **Oil prices** impact overall sales (Ecuador's economy is oil-dependent)
- **Holiday seasons** show measurable sales spikes
- The model helps store managers plan **staffing and stock** in advance
- Forecasting reduces **overstocking losses** and improves **cash flow planning**

---

## 🛠️ Tools & Libraries

| Tool | Purpose |
|------|---------|
| Python 3.x | Core language |
| pandas | Data manipulation |
| NumPy | Numerical operations |
| scikit-learn | ML models and evaluation |
| Matplotlib | Data visualization |
| Anaconda / Jupyter | Development environment |

---

## 👤 Author
Dakalo Mudau

[![GitHub](https://img.shields.io/badge/GitHub-vhogod-181717?style=flat&logo=github)](https://github.com/vhogod)
