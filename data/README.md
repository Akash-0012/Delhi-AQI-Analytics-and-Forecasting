# Data Directory

This folder contains the datasets required to reproduce the complete **Delhi AQI Analytics and Forecasting** project.

The study integrates four real-world environmental datasets to investigate whether **biomass burning** or **meteorological conditions** have a greater influence on Delhi's next-day air quality.

---

# Data Sources

| Dataset | Source | Purpose |
|----------|--------|---------|
| Delhi AQI | CPCB (via Kaggle) | Air Quality Measurements |
| NASA FIRMS | NASA FIRMS (VIIRS) | Biomass Burning Activity |
| ERA5 Wind | Copernicus Climate Data Store | Wind Transport |
| ERA5 Weather | Copernicus Climate Data Store | Local Weather Conditions |

---

# Study Period

**01 January 2015 – 01 July 2020**

All datasets were aligned to this common study period before analysis.

---

# Study Location

The study focuses on **Delhi, India**.

For ERA5 weather extraction, the nearest available reanalysis grid point was selected.

| Parameter | Value |
|-----------|--------|
| Latitude | **28.50° N** |
| Longitude | **77.25° E** |

This grid point represents the meteorological conditions over Delhi throughout the study period.

---

# Dataset 1 — Delhi Air Quality (CPCB)

### Source

Kaggle (Originally collected from the Central Pollution Control Board)

Dataset

```
city_day.csv
```

### Raw Dataset

- 16 Columns
- All Indian Cities

### Delhi Subset

- 2,009 Records
- Date Range:
  - 2015-01-01
  - 2020-07-01

### After Cleaning

- 1,999 Records
- 15 Columns

Cleaning performed:

- Removed **Xylene**
- Removed rows with missing AQI
- Filled missing PM2.5 values
- Filled missing PM10 values

### Variables Used

- Date
- AQI
- AQI_Bucket
- PM2.5
- PM10

### Purpose

This dataset represents the **observed air quality** in Delhi and serves as the primary outcome variable.

AQI is later transformed into the prediction target (**AQI_next_day**) for machine learning.

---

# Dataset 2 — NASA FIRMS Fire Activity

### Source

NASA FIRMS

https://firms.modaps.eosdis.nasa.gov/

Dataset

```
fire_archive_SV-C2_774473.csv
```

### Sensor

VIIRS

### Raw Dataset

- 562,486 Fire Records

### Study Area

Punjab, Haryana and surrounding regions influencing Delhi.

### Cleaning

Removed:

- Local fires occurring inside Delhi

Remaining:

- 560,115 Fire Records

### Why were Delhi fires removed?

The objective of the research is to investigate **external biomass burning** transported into Delhi rather than pollution generated within Delhi itself.

### Variables Used

- Latitude
- Longitude
- Acquisition Date
- Fire Radiative Power (FRP)
- Brightness
- Confidence

### Daily Features Generated

- Fire_Count
- Total_FRP
- Distance_Weighted_FRP
- Fire_Bearing

---

# Dataset 3 — ERA5 Wind Data

### Source

Copernicus Climate Data Store

Product:

ERA5 Reanalysis

### Raw Dataset

Approximately

```
2.5 Million Records
```

The original download contains a 17 × 17 spatial grid over North India with four observations per day.

### Extraction Point

| Latitude | Longitude |
|-----------|-----------|
| **28.50° N** | **77.25° E** |

### After Cleaning

- 8,768 Records

### Variables Used

- u10
- v10

### Daily Features Generated

- Wind Speed
- Wind Direction

### Purpose

Wind data represents the **transport mechanism** responsible for carrying smoke from surrounding fire events toward Delhi.

---

# Dataset 4 — ERA5 Weather Data

### Source

Copernicus Climate Data Store

Product

ERA5 Reanalysis

### Raw Dataset

Approximately

```
2.95 Million Records
```

### Extraction Point

| Latitude | Longitude |
|-----------|-----------|
| **28.50° N** | **77.25° E** |

### After Cleaning

- 10,228 Records

### Variables Used

- Temperature (2 m)
- Dew Point (2 m)

### Derived Features

- Temperature (°C)
- Relative Humidity

### Purpose

Weather variables represent the competing hypothesis that meteorological conditions influence AQI independently of biomass burning.

---

# Data Integration (ETL Pipeline)

The project follows a complete ETL workflow.

## Extract

- Delhi AQI
- NASA FIRMS
- ERA5 Wind
- ERA5 Weather

↓

## Transform

- Cleaning
- Missing Value Treatment
- Unit Conversion
- Daily Aggregation
- Feature Engineering

↓

## Load

Final integrated daily dataset for analytics and machine learning.

---

# Final Integrated Dataset

The four datasets are merged using the **Date** column.

Final variables include:

```
Date
PM2.5
PM10
AQI
Fire_Count
Total_FRP
Distance_Weighted_FRP
Fire_Bearing
Wind_Speed
Wind_Direction
Temperature
Relative_Humidity
```

Each row represents **one day in Delhi**, combining pollution measurements, surrounding fire activity, wind transport, and local weather conditions.

---

# Reproducing the Project

1. Extract `raw_data.zip`
2. Place the datasets inside the `data/` directory.
3. Run the notebooks sequentially:

```
01_Data_Understanding
02_Data_Preprocessing
03_Exploratory_Data_Analysis
04_Feature_Engineering
05_Statistical_Analysis_and_Feature_Validation
06_Machine_Learning
07_Model_Interpretation_and_Research_Findings
```

Intermediate datasets are generated automatically and therefore are **not included** in the repository.

---

# Data Providers

- Central Pollution Control Board (CPCB)
- NASA FIRMS
- Copernicus Climate Data Store (ERA5)

Please refer to the respective providers for licensing and data usage policies.

## Dataset Licensing

This repository includes code developed by the author under the MIT License.

The datasets used in this project are provided by their respective organizations and remain subject to their original licenses and terms of use.

- CPCB Air Quality Data (via Kaggle)
- NASA FIRMS
- Copernicus Climate Data Store (ERA5)

Users should refer to the original data providers for licensing and redistribution policies.