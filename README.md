# Household Energy Consumption Time Series Forecasting

**Short-term household energy usage prediction using historical patterns.**

This project focuses on forecasting hourly household energy consumption using the famous **Household Power Consumption Dataset** from UCI. It demonstrates a complete time series forecasting pipeline with classical and modern machine learning approaches.

---

## 🎯 Objective

- Parse and resample time series data to hourly frequency
- Engineer rich time-based and lag features
- Build and compare three forecasting models: **ARIMA**, **Prophet**, and **XGBoost**
- Evaluate performance using MAE and RMSE
- Visualize actual vs predicted energy usage

---

## 📊 Dataset

- **Source**: [UCI Machine Learning Repository](http://archive.ics.uci.edu/dataset/235/individual+household+electric+power+consumption)
- **Time Period**: December 2006 to November 2010
- **Frequency**: Originally minute-level, resampled to **hourly**
- **Target Variable**: `Global_active_power` (kilowatts)

**Key Columns:**
- `Global_active_power`
- `Global_reactive_power`
- Voltage, Global_intensity
- Sub-metering (kitchen, laundry, water heater/AC)

---

## ✨ Features Engineered

- **Time Features**: Hour, Day of Week, Month, Is Weekend
- **Cyclical Features**: Sine/Cosine encoding for hour and day
- **Lag Features**: 1h, 2h, 3h, 6h, 12h, 24h lags (Critical for performance)
- **Rolling Statistics**: 24-hour rolling mean and standard deviation

---

## 🛠️ Models Implemented

| Model       | Type                  | Key Strengths                     |
|-------------|-----------------------|-----------------------------------|
| **ARIMA**   | Statistical           | Good for linear trends            |
| **Prophet** | Additive Model        | Excellent at handling seasonality |
| **XGBoost** | Gradient Boosting     | Best overall with lag features    |

**Hyperparameter Tuning** applied to XGBoost using `GridSearchCV` with TimeSeriesSplit.

---

## 📈 Results

**Model Performance Comparison:**

*(Example results - actual numbers may vary)*

| Model                | MAE (kW)   | RMSE (kW)  |
|----------------------|------------|------------|
| ARIMA                | 0.312      | 0.478      |
| Prophet              | 0.285      | 0.421      |
| **XGBoost (Tuned)**  | **0.198**  | **0.312**  |

**XGBoost with lag features consistently outperforms the others.**

---

## 🚀 How to Run (Google Colab)

### Option 1: Quick Start (Recommended)
1. Open [Google Colab](https://colab.research.google.com/)
2. Create a new notebook
3. Copy all cells from the Colab version of this project
4. Run cells sequentially

### Option 2: Download Project
```bash
git clone https://github.com/sunilakiran/energy-forecasting.git
cd energy-forecasting
