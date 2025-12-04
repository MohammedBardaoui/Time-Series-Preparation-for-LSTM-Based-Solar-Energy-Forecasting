# 🔆 Solar PV Production Data Preparation for LSTM Forecasting

## 📝 Overview
This project focuses on preparing high-frequency photovoltaic (PV) solar production data (2019–2024) for deep learning forecasting using LSTM models.  
The workflow includes data cleaning, outlier detection, normalization, feature engineering, chronological dataset splitting, and LSTM sequence structuring.

---

## 🎯 Objective
Prepare a high-quality time-series dataset suitable for LSTM-based forecasting by performing:

- Data cleaning & filtering  
- Outlier detection (DBSCAN + univariate checks)  
- Feature engineering  
- Normalization & scaling  
- Train/validation/test splitting  
- Reshaping into LSTM format: **(samples, sequence_length, features)**  

---

## 📂 Dataset Description

- **Time period:** 2019 → 2024  
- **Sampling frequency:** every 5 minutes  
- **Variables of interest:**  
  - Global Horizontal Irradiance (GHI)  
  - Active Power  
- **Night-time measurements removed** (only sunrise → sunset retained)

---

## 🛠️ Workflow

### **1. Data Cleaning**
- Handle missing values  
- Fix inconsistent or erroneous entries  
- Remove night-time rows  
- Detect outliers:  
  - **Univariate methods**  
  - **Multivariate DBSCAN** on (GHI, Active Power)

### **2. Feature Engineering**
- Add time-based features (hour, day of year…)  
- Optional: rolling statistics, lag features, clear-sky index  

### **3. Normalization**
- Apply MinMaxScaler or StandardScaler  

### **4. Dataset Splitting (Chronological)**

| Set           | Years        |
|---------------|--------------|
| **Train**     | 2019–2020    |
| **Validation**| 2021         |
| **Test**      | 2023         |

### **5. LSTM Reshaping**
Prepare sliding-window sequences for deep learning models.

---

## 📁 Project Structure

