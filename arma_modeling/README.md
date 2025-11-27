# ARMA Modeling  
*A practical study of autoregressive and moving average models applied to financial time series.*

[**ARMA Modeling Report**](https://drive.google.com/file/d/1f8RKfl2IlKWku6SDho6zXx6anQDJXRU7/view?usp=drive_link)

---

## 📘 Overview
This project focuses on the **estimation and comparison of AR and ARMA models** for the CAC40 stock index.  
It was conducted as part of the **M1 ECAP 2024–2025 Econometrics course**, under the supervision of **Benoît Sévi**, and developed by **Arthur Ernoult and Florian Crochet**.

**Objectives**
- Estimate autoregressive models (AR(1), AR(2)) using both OLS and maximum likelihood  
- Compare model performance via AIC and BIC information criteria  
- Identify the best ARMA specification for financial return series  
- Conduct diagnostic tests (Ljung–Box, Bartlett) to validate model adequacy  

---

## ⚙️ Features
- Estimation of AR(1) and AR(2) models using both regression and `Arima()` functions  
- Automated ARMA(p, q) model comparison based on AIC and BIC  
- Visualization of returns, autocorrelation (ACF), and partial autocorrelation (PACF)  
- Diagnostic tests on residuals to assess model specification  
- Full reproducibility using R and tidyverse tools  

---

## 🧰 Tech Stack
**Language:** R  
**Libraries:** `tidyverse`, `forecast`  

---

## ⚙️ Installation
Clone the repository and open the R project file:

```bash
git clone https://github.com/<your-username>/TD2_ARMA_Modeling.git
cd TD2_ARMA_Modeling
```

Make sure the following R packages are installed:

```r
install.packages(c("tidyverse", "forecast"))
```

---

## 📚 Usage Example

```r
# Load dataset
CAC40 <- read_csv2("data/CAC40_2010_2023.csv")

# Estimate AR(1) model
lm_modele_ar1 <- lm(Rendement_t ~ Rendement_t_1, data = CAC40)
summary(lm_modele_ar1)

# Compare ARMA(p, q) models
arma_1_0 <- Arima(CAC40$Rendement_t, order = c(1, 0, 0))
arma_0_0 <- Arima(CAC40$Rendement_t, order = c(0, 0, 0))
```

Additional examples and graphs are available in the R Markdown source.

---

## 📂 Project Structure

```
TD2_ARMA_Modeling/
│
├── data/                 # CAC40_2010_2023.csv (weekly index data)
├── code/                 # R scripts for AR and ARMA modeling
├── TD2_ERNOUL_CROCHET.pdf  # Final report with results and interpretations
├── Support2_Series_temporelles_univariees_M1ECAP_2024-2025.pdf  # Course instructions
└── README.md
```

---

## 📊 Results
Main findings:
- The **AR(1)** model performs best, confirmed by both OLS and ARIMA estimation.  
- The **AIC** criterion identifies **ARMA(1,0)** as the best model, while **BIC** suggests **ARMA(0,0)**.  
- Diagnostic tests (Ljung–Box and Bartlett) indicate that **ARMA(1,0)** is well specified and statistically significant.  

> A complete set of results, including ACF/PACF plots and test outputs, is included in the report.

---

## 🧠 References
For theoretical background:
- Hyndman & Athanasopoulos, *Forecasting: Principles and Practice*  
- Hamilton, *Time Series Analysis*  
- Wooldridge, *Introductory Econometrics: A Modern Approach*  
- Sévi, B. (2024). *Support de Cours M1 ECAP – Séries temporelles univariées*  

---

## 📜 License
This project is released under the **MIT License**.  
© 2025 Arthur Ernoult de La Provôté and Florian Crochet 

---

## 👤 Authors
**Arthur Ernoult de La Provôté**  
[GitHub Profile](https://github.com/ArthurEDLP)  

**Florian Crochet**  
[GitHub Profile](https://github.com/floriancrochet)

*Master 1 – Econometrics & Statistics, Applied Econometrics Track*

---

## 💬 Acknowledgments
Thanks to **Benoît Sévi** for course supervision and guidance, and to the R open-source community for providing robust econometric tools.
