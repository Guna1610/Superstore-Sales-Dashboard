# 🛒 Superstore Analytics & Sales Forecasting

This repository contains two projects analyzing the Superstore dataset:
1. **Tableau Dashboard** — interactive visualization of sales performance and trends.  
2. **Sales Forecasting (Python)** — baseline forecasting models (Naive, Moving Average, SARIMAX) to predict future sales.  
---

## 📂 Project 1: Superstore Tableau Dashboard

### 🔹 Problem
The management team of Superstore wants a consolidated dashboard to track:  
- Regional sales performance  
- Top-performing categories & sub-categories  
- Profitability trends  
- Customer segmentation  

### 🔹 Tools
- Tableau  
- Excel (data preparation)  

### 🔹 Deliverables
- Cleaned and prepared dataset in Excel  
- Published interactive Tableau dashboard  

### 🔹 Dashboard Screenshot
![Superstore Tableau Dashboard](results/superstore_dashboard.png)

### 🔹 Key Insights
- **West Region** generated the highest sales.  
- **Technology** was the top-performing category, while **Furniture** had thinner profit margins.  
- A small segment of customers contributed disproportionately to total revenue.  

---

## 📂 Project 2: Sales Forecasting (Python, Baseline Models)

### 🔹 Problem
Forecast monthly sales for the next 3 months to help inventory planning and promotional strategies.

### 🔹 Dataset
- Source: Superstore Orders (aggregated to monthly sales)  
- Period: Jan 2014 – Jun 2017 (~42 months of data)  
- Columns: `date`, `sales`

### 🔹 Tools
- Python (pandas, matplotlib, scikit-learn, statsmodels)  
- Forecasting Models: **Naive, Moving Average, SARIMAX**  

### 🔹 Model Comparison

| Model        | MAE     | RMSE     | MAPE   |
|--------------|---------|----------|--------|
| Naive        | 13,666.8 | 14,142.2 | 20.1% |
| Moving Average   | 11,636.6 | 13,913.4 | 15.7% |
| SARIMAX (0,1,1)(0,1,1,12) | 13,777.7 | 15,422.5 | 18.8% |

➡️ **Moving Average baseline performed the best**, with the lowest error rates.  
➡️ SARIMAX was tested but did not outperform the simpler baseline (likely due to small dataset size).  

---

### 🔹 Forecasts (Next 3 Months — Moving Average)
| Date       | Forecast Sales |
|------------|----------------|
| 2017-07-31 | 70592.199333   |
| 2017-08-31 | 70592.199333   |
| 2017-09-30 | 70592.199333   |

📌 Replace with actual forecast values from your `forecast_next_3months_movingavg.csv`.

### 🔹 Visualization
![Baseline Forecast Comparison](results/actual_vs_forecast_all_baselines.png)  
![Moving Average Forecast](results/actual_vs_forecast_movingavg.png)

---

### 🔹 Key Insights
- Sales are relatively stable — simple smoothing (Moving Average) captured patterns better than SARIMAX.  
- Forecasts suggest **steady sales in the upcoming quarter**.  
- Recommendation:  
  - Maintain inventory at current levels.  
  - Run promotions strategically to stimulate growth.  
  - Automate Moving Average as baseline and keep SARIMAX/ML models under monitoring.  

---

## 🛠️ How to Run

### Tableau Dashboard
1. Download `.twbx` file from `tableau/` folder.  
2. Open in Tableau Desktop or Tableau Public.

### Sales Forecasting
1. Clone repo & install requirements:
   ```bash
   pip install -r requirements.txt
