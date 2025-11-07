# TD3 – Seasonal Time Series Modeling  
*Simulation and estimation of SARMA/SARIMA models with seasonal behavior in R.*

---

## 📘 Overview
This project explores the **development, simulation, and estimation of seasonal time series models (SARMA and SARIMA)**.  
It was conducted as part of the **M1 ECAP Econometrics and Statistics** coursework, under the supervision of **Benoît Sévi**, at the University of Nantes (2024–2025).

**Objectives**
- Simulate and analyze **seasonal ARMA models** with different periodicities  
- Fit SARIMA models and evaluate residual diagnostics  
- Apply seasonal time series analysis to **real economic data**:  
  - French natural gas consumption (2008–2024)  
  - Toulouse-Blagnac airport traffic (1993–2008)  
- Compare alternative model specifications and validate via **ACF/PACF** and **Ljung–Box tests**

---

## ⚙️ Features
- Implementation of **SARMA(p,q)(P,Q)[s]** and equivalent **ARMA(p,q)** formulations  
- Use of `astsa`, `forecast`, and `tidyverse` for simulation and model estimation  
- Diagnostic tools: ACF, PACF, and white-noise testing  
- Comparative analysis based on **AIC/BIC** and residual structure  
- Real-world case studies demonstrating **seasonality and trend modeling**

---

## 🧰 Tech Stack
**Language:** R  
**Libraries:** `astsa`, `forecast`, `tidyverse`

> The environment was built under R version 4.4.3.  
> Code reproducibility ensured with fixed seeds (`set.seed(123)`).

---

## ⚙️ Installation
Clone the repository and open the R project:

```bash
git clone https://github.com/<your-username>/TD3_Saisonnalite.git
cd TD3_Saisonnalite
```

Then install required R packages:

```r
install.packages(c("astsa", "forecast", "tidyverse"))
```

---

## 📚 Usage Example

```r
library(astsa)
library(forecast)
library(tidyverse)

# Simulation of a seasonal ARMA model
set.seed(123)
sarma1 <- sarima.sim(
  ar = c(0.4),
  ma = c(0.3, 0.3),
  sar = c(0.4),
  sma = c(0.3),
  S = 4,
  n = 500
)

# Model fitting
mod <- Arima(sarma1, order = c(1,0,2), seasonal = list(order = c(1,0,1), period = 4))

# Residual diagnostics
Acf(residuals(mod))
Pacf(residuals(mod))
Box.test(residuals(mod), lag = 20, type = "Ljung-Box")
```

---

## 📂 Project Structure

```
TD3_Saisonnalite/
│
├── data/                         # Gas consumption and airport traffic datasets
├── code/                         # R scripts for model simulation and analysis
│   └── code_uts_3.Rmd
├── TD3_HERVE_CROCHET.pdf         # Final report
├── Support3_Series_temporelles…  # Course material
└── README.md
```

---

## 📊 Results

### 1. Simulated Models
- **SARMA(1,2)(1,1)[4]**, **SARMA(1,1)(1,1)[6]**, and **SARMA(2,0)(0,1)[12]** were simulated.  
- Equivalent non-seasonal ARMA forms were derived: ARMA(5,6), ARMA(7,7), ARMA(2,12).  
- Residual diagnostics confirmed white-noise behavior in all final models.

### 2. Gas Consumption (2008–2024)
- Detected strong **annual seasonality** with no trend.  
- Best model: **SARIMA(2,0,0)(0,2,4)[12]**, validated by Ljung–Box (p-value > 0.05) and lowest AIC/BIC.

### 3. Toulouse-Blagnac Airport (1993–2008)
- Identified **trend break in 2001** due to external shock (9/11).  
- Modeling separated pre- and post-2001 periods.  
- Compared **seasonal differencing** and **SARIMA models**, selecting SARIMA(3,0,2)(1,1,1)[12] as optimal.

---

## 🧠 References
- Hyndman & Athanasopoulos, *Forecasting: Principles and Practice*  
- Hamilton, *Time Series Analysis*  
- Wooldridge, *Introductory Econometrics: A Modern Approach*  
- Support course: *Séries temporelles univariées — M1 ECAP, 2024–2025* by Benoît Sévi

---

## 📜 License
This project is released under the **MIT License**.  
© 2025 Florian Crochet, Isaline Hervé

---

## 👤 Author
**Florian Crochet**  
*Econometrics & Statistics Student | Time Series & Financial Modeling*  
📫 [LinkedIn](> À compléter) | [Email](> À compléter) | [Portfolio](> À compléter)

Collaborator: **Isaline Hervé**

---

## 💬 Acknowledgments
Thanks to **Benoît Sévi** for academic supervision and to the **University of Nantes M1 ECAP program** for providing data and methodological support.
