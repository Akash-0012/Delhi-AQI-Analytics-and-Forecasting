<div align="center">

# 🌍 Delhi AQI Analytics & Forecasting
### Investigating the Impact of Biomass Burning and Weather on Delhi's Air Quality

[![Python](https://img.shields.io/badge/Python-3.11-blue?logo=python)](https://www.python.org/)
[![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-black?logo=pandas)](https://pandas.pydata.org/)
[![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-Machine%20Learning-orange?logo=scikit-learn)](https://scikit-learn.org/)
[![Power BI](https://img.shields.io/badge/Power%20BI-Visualization-yellow?logo=powerbi)](https://powerbi.microsoft.com/)
[![SHAP](https://img.shields.io/badge/Explainable%20AI-SHAP-red)](https://shap.readthedocs.io/)
[![License](https://img.shields.io/badge/License-MIT-green)]()

**An end-to-end Data Analytics project integrating environmental datasets to analyze, explain, and forecast Delhi's next-day Air Quality Index (AQI).**

</div>

---

# 📖 Table of Contents

- Project Overview
- Business Problem
- Research Objectives
- Research Hypotheses
- Project Workflow
- Dataset Overview
- ETL Pipeline
- Exploratory Data Analysis
- Feature Engineering
- Statistical Analysis
- Machine Learning
- Model Performance
- Explainable AI (SHAP)
- Key Findings
- Repository Structure
- Installation
- Future Improvements

---

# 🌍 Project Overview

Delhi experiences some of the highest pollution levels in the world. While crop residue burning is often blamed for severe pollution episodes, meteorological conditions such as wind, humidity and temperature also play an important role.

This project investigates:

> **"To what extent do surrounding biomass-burning events influence Delhi's air quality compared with local meteorological conditions?"**

Instead of building only a prediction model, the project follows a complete **Data Analytics workflow**, beginning with problem understanding and ending with interpretable machine learning.

---

# 💼 Business Problem

Air pollution affects millions of people every year.

Government agencies require reliable methods to:

- Monitor pollution trends
- Understand pollution drivers
- Identify high-risk periods
- Improve environmental decision making
- Forecast future AQI levels

This project demonstrates how historical environmental data can be transformed into actionable insights using analytics and predictive modelling.

---

# 🎯 Research Objectives

- Integrate multiple environmental datasets into a unified analytical dataset.
- Investigate relationships between biomass burning, weather conditions and air quality.
- Identify seasonal and temporal pollution patterns.
- Engineer meaningful predictive features.
- Forecast next-day AQI using Machine Learning.
- Interpret model predictions using Explainable AI.

---

# 🔬 Research Hypotheses

### H1

Higher biomass-burning activity surrounding Delhi contributes to increased AQI.

### H2

Meteorological conditions significantly influence pollution accumulation.

### H3

Combining pollution history, fire activity and weather improves next-day AQI prediction.

---

# 🔄 Project Workflow

```
Raw Data
│
├── Delhi AQI
├── NASA FIRMS
├── ERA5 Wind
└── ERA5 Weather
        │
        ▼
Extract
        │
        ▼
Transform
│
├── Cleaning
├── Missing Value Treatment
├── Daily Aggregation
├── Feature Engineering
└── Dataset Integration
        │
        ▼
Exploratory Data Analysis
        │
        ▼
Statistical Analysis
        │
        ▼
Machine Learning
        │
        ▼
Model Interpretation (SHAP)
        │
        ▼
Research Findings
```

---

# 📊 Dataset Overview

| Dataset | Purpose |
|----------|---------|
| Delhi AQI | Pollution Measurements |
| NASA FIRMS | Biomass Burning |
| ERA5 Wind | Smoke Transport |
| ERA5 Weather | Meteorological Conditions |

Study Period

**2015 – 2020**

---

# ⚙️ ETL Pipeline

The project follows an end-to-end ETL workflow.

### Extract

- Delhi AQI
- NASA FIRMS
- ERA5 Weather

### Transform

- Data Cleaning
- Missing Value Treatment
- Date Alignment
- Daily Aggregation
- Feature Engineering
- Feature Validation

### Load

Integrated analytical dataset containing one record per day.

---

# 📈 Exploratory Data Analysis

Key analyses performed include:

- Air quality trend analysis
- Seasonal pollution analysis
- Monthly pollution distribution
- Fire activity trends
- Weather pattern analysis
- Correlation analysis
- Distribution analysis
- Outlier detection
- Time-series visualization

---

# 🛠 Feature Engineering

Created predictive variables including:

### Temporal Features

- Month
- Season
- Day of Week

### Lag Features

- AQI Lag 1
- AQI Lag 2
- AQI Lag 3

### Rolling Features

- Rolling Mean
- Rolling Standard Deviation

### Fire Features

- Fire Count
- Total FRP
- Mean FRP
- Maximum FRP

### Weather Features

- Wind Speed
- Relative Humidity
- Temperature
- Dew Point

---

# 📐 Statistical Analysis

Performed statistical validation through:

- Correlation Analysis
- Feature Importance
- Environmental Feature Comparison
- Time-Series Validation

The statistical analysis helped identify variables with the greatest influence on future AQI while validating research hypotheses.

---

# 🤖 Machine Learning

Models Compared

- Linear Regression
- Random Forest
- XGBoost

Validation Strategy

- Chronological Train-Test Split
- TimeSeriesSplit Cross Validation
- GridSearchCV Hyperparameter Optimization

---

# 📈 Final Model Performance

| Metric | Value |
|----------|--------|
| Model | Random Forest |
| MAE | 28.34 |
| RMSE | 39.63 |
| R² Score | **0.8767** |

---

# 🔍 Explainable AI

Model interpretation was performed using:

- Feature Importance
- SHAP (SHapley Additive exPlanations)

These techniques explain how environmental and temporal variables contribute to model predictions, making the forecasting process transparent and interpretable.

---

# 💡 Key Findings

- Historical AQI remains the strongest predictor of next-day AQI.
- Meteorological variables contribute more consistently than fire activity across the study period.
- Biomass burning still provides additional predictive information, particularly during high-fire periods.
- Integrating multiple environmental datasets improves forecasting capability compared with relying on pollution measurements alone.

---

# 📂 Repository Structure

```
Delhi-AQI-Analytics-and-Forecasting
│
├── data
├── notebooks
├── images
├── README.md
├── requirements.txt
└── .gitignore
```

---

# 🚀 Installation

```bash
git clone https://github.com/yourusername/Delhi-AQI-Analytics-and-Forecasting.git

cd Delhi-AQI-Analytics-and-Forecasting

pip install -r requirements.txt
```

Run notebooks sequentially from **01 → 07**.

---

# 🔮 Future Improvements

- Automate data collection using CPCB, NASA FIRMS and ERA5 APIs.
- Build a real-time ETL pipeline.
- Deploy an interactive Streamlit dashboard.
- Retrain the model periodically using new observations.
- Develop a live AQI forecasting web application.

---

# 👨‍💻 Author

**Akash Singh**

MCA Student | Data Analytics & Machine Learning Enthusiast

GitHub: *(Add your profile link)*

LinkedIn: *(Add your profile link)*

---

## ⭐ If you found this project useful, consider giving it a star!