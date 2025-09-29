#  Patient Readmission Forecasting

##  Project Overview
Hospital readmissions are costly and place a strain on healthcare resources. This project applies **time series forecasting models** to predict daily hospital readmission counts.  
The goal is to provide insights that help hospitals **plan resources, allocate staff, and improve patient care** in advance.  

---

##  Dataset
The dataset contains hospital admission records with both time-series counts and patient-level clinical variables.

**Key Columns:**
- `eid` : Unique patient encounter ID  
- `vdate` : Admission date  
- `rcount` : Readmission count (daily aggregated)  
- `gender` : Patient gender  
- `dialysisrenalendstage` : Dialysis/renal condition indicator  
- `asthma`, `irondef`, `pneum` : Comorbidities (binary)  
- `substancedependence` : Substance dependence indicator  
- `psychologicaldisordermajor` : Major psychological disorder indicator  
- `glucose`, `bloodureanitro`, `creatinine` : Lab values  
- `bmi`, `pulse`, `respiration` : Vitals  
- `lengthofstay` : Length of hospital stay (days)  
- `discharged` : Discharge status  
- `facid` : Facility ID  

---

##  Methods
We explored multiple **time series forecasting models**:
- **ARIMA** – baseline autoregressive model for stationary series  
- **SARIMA** – extends ARIMA by handling seasonality  
- **SARIMAX** – SARIMA with exogenous predictors (e.g., vitals, comorbidities)  
- **Holt-Winters (Exponential Smoothing)** – trend + seasonality smoothing method  
- **Prophet (Facebook/Meta)** – interpretable trend + seasonality modeling  

**Steps:**
1. Data preprocessing (date formatting, null handling, aggregation).  
2. Exploratory Data Analysis (EDA) – trend, volatility, seasonality check.  
3. Stationarity testing (ADF test).  
4. Model training and hyperparameter tuning.  
5. Evaluation using **RMSE, MAE**.  
6. Forecast visualization (actual vs predicted).  

---

##  Results
- Seasonality observed: **weekly patterns** in readmissions.  
- **SARIMAX** and **Prophet** gave the most accurate and interpretable forecasts.  
- Forecasts can help predict peaks, enabling **better staffing and bed management**.  


