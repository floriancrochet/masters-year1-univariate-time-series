# Time Series Forecasting Models Evaluation  
*A study on the evaluation of AR(1) forecasting models using rolling windows for wheat futures returns.*

---

## 📘 Overview
This project focuses on the **evaluation of univariate time series forecasting models** applied to **daily wheat futures returns** between 2006 and 2022.  
It was developed as part of the *M1 ECAP (2024–2025)* program at the University of Nantes, under the supervision of **Benoît Sévi**.

**Objectives**
- Model financial returns using autoregressive (AR) processes  
- Generate and compare 1-day and 5-day forecasts using rolling estimation windows  
- Evaluate model accuracy via **Mincer–Zarnowitz** and **Diebold–Mariano** tests  
- Compare alternative forecasting approaches with a **random walk** benchmark  

---

## ⚙️ Features
- Data preprocessing and visualization of wheat futures returns (2006–2022)  
- AR(1) model specification and estimation  
- Rolling-window forecasting using 10-year and 3-year samples (A10, A3)  
- Forecast evaluation at 1-day and 5-day horizons  
- Implementation of:
  - **Mincer–Zarnowitz test** for unbiasedness of forecasts  
  - **Diebold–Mariano test** with MSE, MAD, and Quad-Quad loss functions  

---

## 🧰 Tech Stack
**Language:** R  
**Libraries:** `tidyverse`, `readxl`, `tseries`, `forecast`, `lmtest`, `sandwich`, `gridExtra`

> The analysis and visualizations were implemented entirely in R Markdown.  
> Output files include `.pdf` reports generated with LaTeX integration.

---

## ⚙️ Installation
To reproduce the analysis:

```bash
# Clone the repository
git clone https://github.com/À compléter.git
cd TD5_HOUSSAIS_CROCHET

# Open the R Markdown file
Rscript -e "rmarkdown::render('code uts 5.Rmd', output_format='pdf_document')"
```

> À compléter — provide actual repository name and script file path if applicable.

---

## 📚 Usage Example

In R:

```r
library(forecast)
rend_ble <- read_excel("data/wheat_futures_returns_2006_2022.xlsx")
rend_ble_ts <- ts(rend_ble$return, start = c(2006, 1, 2), frequency = 252)

modele_ar1 <- Arima(rend_ble_ts, order = c(1, 0, 0))
forecast(modele_ar1, h = 5)
```

> Forecasts are computed for both 1-day and 5-day horizons using 10-year and 3-year rolling windows.

---

## 📂 Project Structure

```
TD5_HOUSSAIS_CROCHET/
│
├── data/                                # Wheat futures data (2006–2022)
├── code uts 5.Rmd                       # Main R Markdown analysis script
├── TD5_HOUSSAIS_CROCHET.pdf             # Final project report
├── Support5_Series_temporelles_...pdf   # Course support document
└── README.md                            # Project documentation
```

---

## 📊 Results

### Summary of Findings
- The **ADF test** confirms the **stationarity** of the return series.  
- The **AR(1)** model was selected based on ACF and PACF analysis.  
- Forecasts generated using rolling windows:
  - **A10_1**, **A3_1** (1-day)
  - **A10_5**, **A3_5** (5-day)
- **Mincer–Zarnowitz test** results show that A10_1, A3_1, and A3_5 forecasts are unbiased.  
- **Diebold–Mariano test** results:
  - Random walk model is consistently rejected.
  - **A3_1** slightly outperforms **A10_1**.
- **Best performing models:** A3_1 and A10_1.

---

## 🧠 References
- Hyndman, R. J., & Athanasopoulos, G. (2018). *Forecasting: Principles and Practice.*  
- Hamilton, J. D. (1994). *Time Series Analysis.*  
- Wooldridge, J. M. (2020). *Introductory Econometrics: A Modern Approach.*  
- Sévi, B. (2024). *Support de cours n°5 – Évaluation de modèles de prévision*, Université de Nantes.

---

## 📜 License
This project is released under the **MIT License**.  
© 2025 Florian Crochet, Rémi Houssais

---

## 👤 Authors
**Florian Crochet**  
*Econometrics & Statistics Student | M1 ECAP, Université de Nantes*  
📫 > À compléter (email or LinkedIn)

**Rémi Houssais**  
*Econometrics & Statistics Student | M1 ECAP, Université de Nantes*  
📫 > À compléter (email or LinkedIn)

**Supervisor:**  
Benoît Sévi – [benoit.sevi@univ-nantes.fr](mailto:benoit.sevi@univ-nantes.fr)

---

## 💬 Acknowledgments
This project was conducted as part of the **Univariate Time Series** module (*Séries temporelles univariées – TD5*).  
Special thanks to **Benoît Sévi** for his guidance and to the R open-source community for the analytical tools used.
