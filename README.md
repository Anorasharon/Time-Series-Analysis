# 📈 Stock Market Analysis using Python

> A comprehensive data analysis pipeline for Indian stock market time series using yFinance, NSEPy, and statistical techniques.

---

## 🧠 Overview

This project demonstrates an end-to-end analysis of stock market data from the Indian stock exchange using Python libraries. It involves:

- Downloading data from **Yahoo Finance** (`yfinance`) and **NSE** (`nsepy`)
- Descriptive analysis using a custom `Descriptive` class
- Distribution and standard normal plots
- Time series decomposition (trend, seasonality, residuals)
- ADF (Augmented Dickey-Fuller) test for stationarity
- ACF/PACF plots and lag analysis
- Frequency tables of prices

---

## ⚙️ Setup Instructions

1. ✅ Clone the repository  
2. ✅ Install dependencies

```bash
pip install yfinance nsepy pandas matplotlib seaborn statsmodels
```

3. ✅ Run the notebook  
Open `stock_analysis.ipynb` in Jupyter or any notebook environment.

---

## 🔍 Core Functionality

### 📥 1. Download Stock Data

```python
import yfinance as yf
stk_data = yf.download("RELIANCE.NS", start="2023-01-01", end="2023-07-01")
```

---

### 📊 2. Descriptive Analysis

```python
from Descriptive import Descriptive
obj = Descriptive()
quan, qual = obj.segreQuanQual(stk_data)
des_data = obj.descriptive_Analysis(stk_data, quan)
```

---

### 🧮 3. PDF Probability and Standard Normal Distribution

```python
get_pdf_probability(stk_data["Close"], 1000, 1100)
stdNDGraph(stk_data["Close"])
```

---

### 📋 4. Frequency Table

```python
freqTable("Low", stk_data)
```

---

### 📈 5. Time Series Decomposition

```python
from statsmodels.tsa.seasonal import seasonal_decompose
result = seasonal_decompose(dataset["Close"], model='additive')
result.plot()
```

---

### 🧪 6. ADF Stationarity Test

```python
adf_test(dataset["Close"], dataset, "Close")
```

Sample Output:
```
Test Statistic: -3.007
p-value: 0.034
Conclusion: ✅ Stationary
```

---

### 🔁 7. ACF & PACF Plots

```python
plot_acf(dataset["Close"].tolist(), lags=50)
plot_pacf(dataset["Close"].tolist(), lags=50)
```

---

### 🔂 8. Lag Plot

```python
from pandas.plotting import lag_plot
lag_plot(dataset["Close"], lag=1)
```

---

## 📊 Sample Graphs

- Price over Time
- PDF with shaded area
- Distribution (Z-score)
- ADF Test result graph
- ACF & PACF time correlation

---

## 👩‍💻 Author

**Anora Sharon Tessie**  
📧 anorasharontessie@gmail.com

---

## 📚 References

- [`yfinance`](https://pypi.org/project/yfinance/)
- [`nsepy`](https://pypi.org/project/nsepy/)
- [Statsmodels Documentation](https://www.statsmodels.org/)
- [Seaborn Statistical Plots](https://seaborn.pydata.org/)

---

## ⚠️ Disclaimer

This project is for **educational purposes only**. Do not use this code for real-world trading decisions without consulting financial experts.

---
