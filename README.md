# 🌍 Delhi AQI Analytics & Forecasting

> **An End-to-End Data Analytics Project Investigating the Impact of Biomass Burning and Meteorological Conditions on Delhi's Air Quality**

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)
![SHAP](https://img.shields.io/badge/SHAP-Explainable_AI-blue?style=for-the-badge)

---

## 📌 Overview

Delhi experiences severe air pollution due to a combination of environmental and human activities. While crop residue burning is often considered a major contributor, meteorological conditions such as wind, humidity and temperature also influence pollution accumulation.

This project develops an end-to-end data analytics workflow that integrates pollution, fire activity and weather datasets to understand the factors affecting Delhi's Air Quality Index (AQI). The analysis is extended with predictive analytics to forecast the next day's AQI and explain model predictions using SHAP.

---

## 📊 Project Summary

| Attribute | Details |
|-----------|----------|
| Domain | Environmental Data Analytics |
| Study Area | Delhi, India |
| Study Period | Jan 2015 – Jul 2020 |
| Data Sources | CPCB, NASA FIRMS, ERA5 Wind & Weather |
| Final Dataset | 1,847 Daily Records |
| Engineered Features | 25 |
| Target Variable | Next-Day AQI |
| Best Model | Random Forest Regressor |
| R² Score | **0.8767** |

---

## 🎯 Objectives

- Integrate multiple environmental datasets into a single analytical dataset.
- Analyze seasonal and temporal pollution patterns.
- Measure the relationship between biomass burning and AQI.
- Evaluate the influence of meteorological conditions on pollution.
- Build an interpretable model to forecast next-day AQI.

---

## 🛠 Skills Demonstrated

- ETL Pipeline
- Data Cleaning & Integration
- Exploratory Data Analysis (EDA)
- Statistical Analysis
- Feature Engineering
- Predictive Analytics
- Explainable AI (SHAP)
- Data Visualization
- Git & GitHub

---

## 🔄 Project Workflow

<p align="center">
<img src="images/project_workflow.png" width="900">
</p>

---

## ⚙️ ETL Pipeline

Four independent real-world datasets were extracted, cleaned, transformed and aggregated to daily observations before being merged into a unified analytical dataset.

The ETL process included:

- Missing value handling
- Unit conversion
- Date standardization
- Daily aggregation
- Dataset integration
- Feature preparation

<p align="center">
<img src="images/etl_pipeline.png" width="900">
</p>

### Data Sources

| Dataset | Purpose |
|----------|---------|
| CPCB Air Quality | AQI & PM2.5 |
| NASA FIRMS | Fire Activity |
| ERA5 Wind | Wind Transport |
| ERA5 Weather | Temperature & Humidity |

---

## 📈 Exploratory Data Analysis

The exploratory analysis focused on understanding seasonal pollution trends and identifying relationships between environmental variables.

Key analyses included:

- Seasonal AQI Trends
- Monthly Pollution Distribution
- Fire Activity Trends
- Weather Analysis
- Correlation Analysis

### Seasonal AQI Trend

<p align="center">
<img src="images/seasonal_aqi_trend.png" width="850">
</p>

**Observation**

- Winter recorded the highest AQI due to stagnant atmospheric conditions.
- Monsoon showed the lowest pollution because rainfall improved pollutant dispersion.

---

### Correlation Analysis

<p align="center">
<img src="images/correlation_heatmap.png" width="850">
</p>

**Observation**

Historical AQI features showed the strongest correlation with future AQI, while weather variables demonstrated stronger relationships than fire activity alone.

---

## 📊 Statistical Analysis

Statistical validation was performed to evaluate relationships between pollution, fire activity and meteorological variables.

The analysis indicated that:

- Weather variables consistently influenced AQI variation.
- Fire activity provided additional predictive information during high-burning periods.
- Historical pollution remained the strongest predictor of next-day AQI.

---

## 🧩 Feature Engineering

Domain-specific features were created to improve forecasting performance.

### Temporal Features

- Month
- Season
- Day of Week

### Historical Pollution Features

- AQI Lag 1
- AQI Lag 2
- AQI Lag 3
- Rolling Mean
- Rolling Standard Deviation

### Fire Features

- Fire Count
- Fire Radiative Power (FRP)
- Lagged Fire Features

### Weather Features

- Temperature
- Dew Point
- Relative Humidity
- Wind Speed
- Wind Components

---

## 🤖 Predictive Analytics

Three regression models were evaluated.

| Model | Purpose |
|--------|----------|
| Linear Regression | Baseline |
| Random Forest | Final Model |
| XGBoost | Performance Comparison |

### Model Performance

| Metric | Score |
|---------|-------|
| MAE | 28.34 |
| RMSE | 39.63 |
| R² Score | **0.8767** |

### Actual vs Predicted AQI

<p align="center">
<img src="images/actual_vs_predicted.png" width="850">
</p>

---

## 🔍 Model Explainability

SHAP (SHapley Additive Explanations) was used to interpret model predictions and identify the contribution of each feature.

<p align="center">
<img src="images/shap_summary.png" width="850">
</p>

The analysis confirmed that historical AQI, dew point, seasonal variation and wind speed were among the most influential variables affecting next-day AQI.

---

## 💡 Key Insights

- Delhi experiences severe seasonal pollution, particularly during winter.
- Meteorological conditions influence AQI more consistently than fire activity alone.
- Biomass burning improves prediction accuracy during agricultural burning periods.
- Integrating pollution, weather and fire datasets provides better forecasting than using pollution history alone.
- SHAP improves model transparency by explaining individual predictions.

---

## 🚀 Future Enhancements

- Automate data collection using CPCB, NASA FIRMS and ERA5 APIs.
- Build a scheduled ETL pipeline for daily updates.
- Deploy an interactive Streamlit dashboard.
- Enable automated next-day AQI forecasting.
- Retrain the model periodically using newly available data.

---

## 📂 Repository Structure

```
Delhi-AQI-Analytics-and-Forecasting/
│
├── data/
│   ├── README.md
│   └── raw_data.zip
│
├── images/
├── notebooks/
│   ├── 01_Data_Understanding.ipynb
│   ├── 02_Data_Preprocessing.ipynb
│   ├── 03_Exploratory_Data_Analysis.ipynb
│   ├── 04_Feature_Engineering.ipynb
│   ├── 05_Statistical_Analysis_and_Feature_Validation.ipynb
│   ├── 06_Machine_Learning.ipynb
│   └── 07_Model_Interpretation_and_Research_Findings.ipynb
│
├── requirements.txt
├── README.md
└── LICENSE
```

---

## ⚡ Installation

```bash
git clone https://github.com/Akash-0012/Delhi-AQI-Analytics-and-Forecasting.git

cd Delhi-AQI-Analytics-and-Forecasting

pip install -r requirements.txt
```

Run the notebooks sequentially:

```
01 → 07
```

---

## 📚 Data Sources

- Central Pollution Control Board (CPCB)
- NASA FIRMS
- Copernicus Climate Data Store (ERA5)

Detailed download instructions are available in **`data/README.md`**.

---

## 👨‍💻 Author

**Akash Singh**

Aspiring Data Analyst | Python | SQL | Machine Learning

- GitHub: https://github.com/Akash-0012
- LinkedIn: *(Add your LinkedIn profile URL)*

---

## 📄 License

This project is licensed under the MIT License. See the `LICENSE` file for details.

⭐ If you found this project useful, consider giving it a star!
