# 🌫️ Time-Series Forecasting of Delhi Air Quality Using Deep Learning

**Author:** [Nilay Singh](https://github.com/n1lays1ngh) 
**Institution:** Thapar Institute of Engineering & Technology  
 

---

## 📌 Project Overview

Air pollution is one of the most pressing environmental and public-health challenges facing New Delhi. This project implements a robust **Deep Learning forecasting system** to predict **next-day Air Quality Index (AQI)** using historical pollution and meteorological data from **2017–2025**.

Multiple advanced neural architectures were developed and benchmarked to identify the most accurate model capable of handling Delhi’s volatile pollution trends and sudden AQI spikes.

The project integrates:
- Advanced **time-series feature engineering**
- **GRU, LSTM, Stacked LSTM**, and **CNN-LSTM** models
- Comprehensive performance evaluation and visual analysis

---

## 📂 Repository Structure

```text
Delhi-Air-Quality-Prediction/
├── Data Preprocessing/         # Scripts for cleaning and scaling raw data
├── Scraped Data/               # Raw AQI + meteorological data (2017–2025)
├── EDA.ipynb                   # Exploratory Data Analysis (seasonality, trends)
├── ModelTraining.ipynb         # LSTM, Stacked LSTM, CNN+LSTM, GRU models
├── Final_Dataset.csv           # Feature-engineered dataset
├── delhi_aqi_cleaned.csv       # Cleaned dataset
├── ML Report Project.pdf       # Full technical report
├── ML PROJECT Presentation.pdf # Project presentation
└── README.md                   # Project documentation
```

---

## 🧠 Methodology

### 1️⃣ Data Collection & Preprocessing
- **Data Source:** Delhi AQI dataset merged with meteorological attributes  
- **Preprocessing Includes:**
  - Handling missing values
  - Outlier removal
  - **MinMax Scaling** to stabilize neural network training

---

### 2️⃣ Feature Engineering

More than **30+ predictive features** were generated to enhance temporal learning:

✔ **Lag Features**
- `AQI_lag_1`
- `AQI_lag_3`
- `AQI_lag_7`

✔ **Rolling Statistics**
- Rolling Mean  
- EWMA (Exponential Weighted Moving Average)

✔ **Cyclical Encoding**
Captures periodic seasonal effects such as winter pollution spikes  
- `Month_sin`, `Month_cos`
- `Day_sin`, `Day_cos`

✔ **Meteorological Flags**
One-hot encoded atmospheric conditions:
- Fog
- Mist
- Haze
- Pollution episodes

---

## 🏗️ Model Architectures Implemented

We implemented and evaluated four major deep learning architectures:

| Model | Description |
|-------|------------|
| **Base LSTM** | Standard single-layer sequential LSTM |
| **Stacked LSTM** | Deep multi-layer LSTM for richer pattern learning |
| **CNN + LSTM** | Convolution for feature extraction + LSTM sequencing |
| **GRU (Best)** | Lightweight gated recurrent model optimized for temporal memory |

---

## 📊 Results & Performance

Models were evaluated using:
- **RMSE** (Lower = Better)
- **R² Score** (Higher = Better)

| Model | RMSE | R² Score | Verdict |
|------|------|---------|--------|
| Base LSTM | 45.42 | 0.7920 | Good baseline |
| Stacked LSTM | 45.22 | 0.7938 | Slight improvement |
| CNN + LSTM | 54.45 | 0.7012 | Over-smoothed, weak at spike prediction |
| **GRU (Best)** | **38.45** | **0.8510** | **Superior accuracy & generalization** |

> **Key Insight:**  
> The **GRU model** proved to be the most effective. Unlike LSTM and CNN-LSTM, it successfully captured extreme AQI surges (e.g., winter & Diwali pollution spikes) while maintaining stable baseline performance.

---

## 📉 Visual & Error Analysis

- **Prediction Curves:** GRU closely tracks real AQI fluctuations  
- **Spike Handling:** GRU demonstrates strong responsiveness to sudden pollution peaks  
- **Residual Distribution:** GRU residuals concentrate tightly around zero → low bias + higher stability  

---

## 🔮 Future Scope

To further enhance system capability:

- Extend forecasting horizon to **3–7 day predictions**
- Integrate **Satellite AOD (Aerosol Optical Depth)** data
- Perform **Bayesian/Optuna hyperparameter tuning**
- Explore **Transformer-based architectures**, including:
  - Temporal Fusion Transformers (TFT)
  - Attention-based models

---

## 🎥 Relevant Learning Resource

To better understand deep learning approaches in time-series forecasting, refer:

**Deep Learning for Time Series Forecasting**  
https://www.youtube.com/watch?v=Te5rM630t0k

---

## 📚 References

1. TensorFlow Official Documentation  
2. “Understanding GRU Networks” – Technical Analysis & Working Principles  
3. Advanced Deep Learning Frameworks for Time-Series Forecasting  

---

### 📌 Course Submission

Project submitted for **UML501 – Machine Learning**  
Thapar Institute of Engineering & Technology

---
