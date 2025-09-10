# AirQualityPrediction
# 🌍 Air Quality Prediction

This project predicts the **Air Quality Index (AQI)** using various pollutant measures such as **PM2.5, PM10, SO2, NOx, NH3, CO, and O3**. The model helps in identifying air pollution severity and forecasting air quality levels for better environmental monitoring.

---

## 📌 Features
- Preprocessing of air quality datasets (handling missing values, date-time parsing, feature engineering).
- Calculation of **Sub-Indexes** for each pollutant using CPCB (India) guidelines.
- Final AQI computed as the **maximum of sub-indices** with rule-based conditions.
- Machine Learning models for AQI prediction.
- Visualization of air pollution trends over time.
- Support for real-time AQI calculation if live data is available.

---

## 🧪 Workflow
1. **Data Collection**  
   - Historical air quality data (CSV or API-based sources such as CPCB, OpenAQ).  

2. **Data Preprocessing**  
   - Convert `Date` column to `datetime`.  
   - Handle missing values (using Sub-Index calculations instead of mean/mode).  
   - Calculate rolling averages for 24-hr pollutants and max values for 8-hr pollutants.  

3. **Sub-Index Calculation**  
   - PM2.5, PM10, SO2, NOx, NH3 → 24-hr average (≥ 16 values).  
   - CO, O3 → 8-hr max values.  
   - Convert pollutant concentrations to Sub-Indexes using AQI breakpoints.  

4. **AQI Calculation**  
   - AQI = **Maximum of Sub-Indexes**, provided:  
     - At least one of PM2.5 or PM10 is available.  
     - At least 3 pollutants are available.  

5. **Model Training**  
   - Train ML models (Random Forest, XGBoost, etc.) to predict AQI.  
   - Evaluate using RMSE, MAE, R².  

6. **Visualization**  
   - Time-series plots of pollutant levels.  
   - AQI distribution by city/region.  
   - Heatmaps of pollutant correlations.  

---

## ⚙️ Installation
```bash
# Clone repository
git clone https://github.com/kireeti-ai/AirQualityPrediction.git
cd AirQualityPrediction

