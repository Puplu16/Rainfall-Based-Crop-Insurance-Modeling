# Designing a Crop Insurance Scheme for Paddy Cultivation in India

A data-driven, three-part framework integrating long-term historical datasets, machine learning, and a financial derivatives framework to design an actuarially sound and affordable crop insurance scheme for Indian paddy farmers.

---

## 👥 Authors & Project Details
* **Author:** Samya Mukherjee (ID No. B2430057)
* **Supervisor:** Prof. Bappaditya Mukhopadhyay (Great Lakes Institute of Management Gurugram)
* **Institution:** Department of Computer Science, Ramakrishna Mission Vivekananda Educational and Research Institute (RKMVERI), Belur Math
* **Course:** MSc in Big Data Analytics

---

## 📊 Project Overview
Paddy cultivation remains highly vulnerable to monsoon variations and erratic market dynamics across India. This project constructs a holistic statistical framework to mitigate income risk by introducing an evidence-based premium determination model. It benchmarks data across 584 districts to ensure localized accuracy.

### 📂 Core Datasets Integrated
The analytical pipeline harmonizes and matches several high-resolution data portals:
1. **ICRISAT Dataset (1966–2015):** Granular district-level data for cultivated rice area, production, and yield.
2. **IMD Monthly Rainfall (1901–2015):** Century-long tracking focusing on the vital Southwest Monsoon (June–September).
3. **Daily Rainfall Portals (2009–2023):** High-frequency metrics to isolate intra-seasonal climate anomalies.
4. **AGMARKNET Mandi Prices (2010–2023):** Variety-specific market transaction values converted to economic metrics.

---

## 🛠️ Computational & Modeling Pipeline
The project implements an end-to-end framework execution in Python using `pandas`, `statsmodels`, `TensorFlow`, and `scipy` across three core phases:

### Part 1: Exploratory & Distributional Analysis
* Validates that monsoon rainfall systematically follows a **Log-Normal Distribution** ($p\text{-value} > 0.95$).
* Establishes a log-transformed multiple regression model showing an overall **Rainfall-to-Yield Elasticity of 0.32**.

### Part 2: Advanced Forecasting (Target Year: 2026)
* **Rainfall Dynamics:** Modeled using an **Exponentially Weighted Moving Average (EWMA)** technique.
* **Yield Predictions:** Benchmarked using a non-linear machine learning approach (**LSTM Networks**) against a classical linear econometric model (**ARIMAX** with market prices as exogenous variables).
* **Price Tracks:** Generated via **ARIMA** modeling to capture distinct regional market fragmentation.

### Part 3: Financial Derivatives Framework for Premium Pricing
* Conceptualizes the insurance contract payout as a **piecewise linear function** resembling a combination of financial digital and spread options.
* Assuming normal yield distribution around the baseline projection, a **closed-form analytical solution** is derived for the expected loss, bypassing the need for computationally heavy Monte Carlo simulations.

---

## 🔑 Key Empirical Results

### 🏆 Predictive Modeling Excellence
A Hybrid Average model merging the patterns of LSTM and ARIMAX architectures yielded the highest predictive strength:
* **Hybrid Model Performance:** $\text{RMSE} = 135.6 \text{ kg/ha}$, $\text{MAE} = 94.2 \text{ kg/ha}$, $R^2 = 0.91$.

### 💰 Actuarial Pricing and Normalization (2026 Crop Season)
To balance systemic underwriting risk with practical farmer affordability, raw technical premiums are continuous-discounted ($r=5\%$) and min-max scaled to a practical range of **₹100 to ₹900 per hectare** across major agrarian states.


| State | Predicted Yield (kg/ha) | Forecasted Price (₹/kg) | Final Scaled Premium (₹/ha) |
| :--- | :---: | :---: | :---: |
| **Punjab** | 8476.52 | 22.91 | **890.00** |
| **Orissa** | 2553.29 | 23.03 | **480.00** |
| **Bihar** | 2137.24 | 22.65 | **450.00** |
| **Tamil Nadu** | 2073.66 | 20.14 | **430.00** |

*Historical and regional outputs calibrated for all ten core states are detailed inside the repository data structures.*

### 📉 Efficiency Comparison vs. PMFBY
* The data-driven actuarial architecture structures premiums that are **28% to 33% lower** than the current Pradhan Mantri Fasal Bima Yojana (PMFBY) benchmarks while securing matching safety nets.
* Greatly reduces geographical basis risk and removes the costly delays associated with traditional physical Crop Cutting Experiments (CCEs).

---
