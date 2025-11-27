# Univariate Time Series Projects  
*A collection of academic projects focused on econometric analysis, simulation, and forecasting of univariate time series.*

---

## 📄 Project Reports (PDF – Online Access)

Each report addresses a specific pillar of univariate time series econometrics, combining theoretical foundations, simulation, and applied empirical analysis.

| Topic | Description |
|-------|-------------|
| [**ARMA Modeling**](https://drive.google.com/file/d/1f8RKfl2IlKWku6SDho6zXx6anQDJXRU7/view?usp=drive_link) | Estimation and comparison of AR and ARMA models on CAC40 returns using OLS and maximum likelihood, with model selection based on AIC/BIC and diagnostic validation via Ljung–Box and Bartlett tests. |
| [**Forecast Evaluation**](https://drive.google.com/file/d/1ALjuejyp1zKzP5QCd0AS1U_dGtCqBv3R/view?usp=drive_link) | Rolling-window evaluation of AR(1) forecasting models for wheat futures returns, benchmarked against random walk models using Mincer–Zarnowitz and Diebold–Mariano tests across multiple horizons. |
| [**Unit Root Analysis**](https://drive.google.com/file/d/1QmdBvLZ--e_MzTy0FGoOjPMDLxj6cd3l/view?usp=drive_link) | Monte Carlo exploration of stochastic trends, unit roots, and spurious regressions, distinguishing deterministic vs stochastic non-stationarity and applied to U.S. GDP data via Dickey–Fuller and KPSS testing. |
| [**Seasonality Modeling**](https://drive.google.com/file/d/1NW7GhvEW0F0v9NsUJB1jogwmfjpTEsls/view?usp=drive_link) | Simulation and estimation of SARMA/SARIMA models applied to gas consumption and airport traffic data, with model comparison based on residual diagnostics, AIC/BIC, and seasonal structure validation. |
| [**Stochastic Processes**](https://drive.google.com/file/d/1ermB-n0d533Lh_V_2GMQBygR_mn3Ufyp/view?usp=drive_link) | Analytical and simulated study of AR, MA, and ARMA processes emphasizing stationarity conditions, characteristic roots, and interpretation of ACF/PACF structures under the lag operator framework. |

---

## 📘 Overview
This project consolidates multiple academic works developed within the **M1 ECAP Econometrics & Statistics** program at the University of Nantes (2024–2025). It provides a comprehensive framework for **modeling, simulating, diagnosing, and forecasting financial and economic time series** using rigorous econometric methodology.

It integrates applied studies on:
- AR, ARMA, SARMA, and SARIMA modeling
- Non-stationarity and unit root detection
- Stochastic process simulation
- Forecast evaluation using statistical tests

All components emphasize **reproducibility, methodological clarity, and empirical validation**.

**Objectives**
- Model and analyze univariate time series using ARMA-family models  
- Simulate stochastic processes and assess stationarity conditions  
- Detect and interpret unit roots and spurious regressions  
- Evaluate forecasts using formal econometric tests  
- Compare competing model specifications using information criteria and diagnostics  

> This README synthesizes all provided project documentations into a single unified description.

---

## ⚙️ Features
- Estimation and comparison of AR and ARMA models (OLS and Maximum Likelihood)  
- Seasonal modeling with SARMA and SARIMA structures  
- Monte Carlo simulation of stochastic processes  
- Stationarity testing (ADF, KPSS, Dickey–Fuller) and spurious regression detection  
- Rolling-window forecasting and benchmark comparison  
- Forecast evaluation with Mincer–Zarnowitz and Diebold–Mariano tests  
- Model comparison via AIC and BIC  
- Residual diagnostics using ACF, PACF, and Ljung–Box tests  
- Visualization of trends, seasonality, and autocorrelation patterns  

> Functional coverage includes financial indices (CAC40), wheat futures, U.S. GDP, gas consumption, and airport traffic data.

---

## 🧰 Tech Stack
**Language:** R  
**Libraries:**  
- tidyverse  
- forecast  
- tseries  
- urca  
- astsa  
- ggplot2  
- FinTS  
- Metrics  
- TSA  
- purrr  
- openxlsx  
- readxl  
- lmtest  
- sandwich  

> All analyses were implemented using R and R Markdown for complete reproducibility.

---

## ⚙️ Installation
Clone the repository:

```bash
git clone https://github.com/À compléter.git
cd À compléter
```

Install required packages in R:

```r
install.packages(c(
  "tidyverse", "forecast", "tseries", "urca", "astsa", "ggplot2",
  "FinTS", "Metrics", "TSA", "purrr", "openxlsx", "readxl",
  "lmtest", "sandwich"
))
```

> Repository name and structure: > À compléter

---

## 📚 Usage Example

```r
library(forecast)

# Example AR(1) estimation
model_ar1 <- Arima(series, order = c(1, 0, 0))
forecast(model_ar1, h = 5)

# Stationarity testing
adf.test(series)
kpss.test(series)

# Seasonal SARIMA estimation
model_sarima <- Arima(series,
  order = c(2,0,0),
  seasonal = list(order = c(0,2,4), period = 12)
)
```

Examples include ARMA modeling of CAC40 returns, SARIMA modeling of gas consumption, and rolling forecasts for wheat futures.

---

## 📂 Project Structure

```
time-series-toolkit/
│
├── data/                 # Financial and economic datasets
├── code/                 # R scripts and R Markdown analyses
├── reports/              # Rendered PDF reports
├── supports/             # Course material and documentation
└── README.md
```

> Exact folder naming: > À compléter  
> Logical structure reflects consistency across all subprojects.

---

## 📊 Results
Key consolidated findings:
- AR(1) consistently outperforms higher-order AR models in CAC40 data.  
- AIC generally selects ARMA(1,0) while BIC may favor simpler models.  
- Unit root presence confirmed in U.S. GDP series, highlighting trend non-stationarity.  
- Spurious regression simulations show rejection rates above 80%.  
- Seasonal models significantly improve forecasts in gas consumption and airport traffic data.  
- Best forecasting performance observed for rolling AR(1) models with 3-year windows.  
- Random walk benchmarks are systematically rejected.

> Diagnostics confirm robust specification through residual whiteness and statistical significance.

---

## 🧠 References
- Hyndman & Athanasopoulos, *Forecasting: Principles and Practice*  
- Hamilton, *Time Series Analysis*  
- Wooldridge, *Introductory Econometrics: A Modern Approach*  
- Sévi, B. (2024–2025). *Séries temporelles univariées – M1 ECAP*

---

## 📜 License
This project is released under the **MIT License**.  
© 2025 Florian Crochet

---

## 👤 Author
**Djayan Daëron**  
[GitHub Profile](https://github.com/Djayan-D)  

**Arthur Ernoult de La Provôté**  
[GitHub Profile](https://github.com/ArthurEDLP)  

**Isaline Hervé**  
[GitHub Profile](https://github.com/Isahrv)  

**Achille Marteret**  

**Rémi Houssais**  

**Florian Crochet**  
[GitHub Profile](https://github.com/floriancrochet)

*Master 1 – Econometrics & Statistics, Applied Econometrics Track*

---

## 💬 Acknowledgments
Special thanks to **Benoît Sévi** for academic supervision and to all academic collaborators involved across the different project modules. Appreciation is also extended to the R open-source community for providing essential analytical tools.
