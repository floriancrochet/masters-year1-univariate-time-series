# Analysis of Non-Stationarity and Unit Roots  
*An applied R-based study of time series stationarity, stochastic trends, and spurious regression.*

[**Unit Roots Analysis Report**](https://drive.google.com/file/d/1QmdBvLZ--e_MzTy0FGoOjPMDLxj6cd3l/view?usp=drive_link)

---

## 📘 Overview
This project explores **the concept of non-stationarity and unit roots** in univariate time series using **Monte Carlo simulations** and **empirical applications**.  
It was developed as part of the *M1 ECAP (Université de Nantes)* course *Series temporelles univariées* supervised by **Benoît Sévi**.

**Objectives**
- Understand the difference between deterministic and stochastic trends  
- Illustrate permanent vs. transitory shocks in AR(1) processes  
- Detect spurious regressions in non-stationary data  
- Estimate and interpret Dickey–Fuller and KPSS tests  
- Apply the methodology to real economic data (U.S. GDP, 1990–2023)

---

## ⚙️ Features
- Simulation of **AR(1)** processes with and without unit roots  
- Visual comparison of **deterministic (TS)** vs. **stochastic (DS)** trends  
- Monte Carlo estimation of **critical values for the Dickey–Fuller test**  
- Empirical analysis of the **U.S. GDP series (1990–2023)**  
- Identification of **spurious regressions** through large-scale simulations  

---

## 🧰 Tech Stack
**Language:** R  
**Libraries:**  
- `tidyverse` — data manipulation and visualization  
- `openxlsx` — Excel data import/export  
- `urca` — unit root and cointegration tests  
- `forecast` — time series modeling tools  
- `tseries` — stationarity and financial econometrics tests  

---

## ⚙️ Installation
Clone the repository and open the R Markdown file in RStudio:

```bash
git clone https://github.com/<your-username>/TD4_CROCHET_MARTERET.git
cd TD4_CROCHET_MARTERET
```

Then, install the required R packages:

```R
install.packages(c("tidyverse", "openxlsx", "urca", "forecast", "tseries"))
```

---

## 📚 Usage Example

```R
# Run the R Markdown analysis
rmarkdown::render("TD4_CROCHET_MARTERET.Rmd", output_format = "pdf")

# Example: Simulate an AR(1) process with a shock
simulate_ar1(phi = 0.9, choc_value = 20, choc_time = 100, n = 200)
```

The notebook includes:
- Exploratory simulations of shocks in AR(1) processes  
- Tests for spurious regressions  
- Monte Carlo estimation of Dickey–Fuller distributions  
- Empirical analysis of U.S. GDP stationarity  

---

## 📂 Project Structure

```
TD4_CROCHET_MARTERET/
│
├── data/                    # Economic datasets (e.g., U.S. GDP 1990–2023)
├── TD4_CROCHET_MARTERET.pdf # Final report (rendered from R Markdown)
├── code uts 4.Rmd           # Main R Markdown source file
├── Support4_Series_temporelles...pdf  # Official assignment instructions
└── README.md
```

---

## 📊 Results
Key findings:

- For **ϕ < 1**, shocks are transitory and the process returns to its mean.  
- For **ϕ = 1**, shocks have **permanent effects**, confirming a random walk behavior.  
- Spurious regression tests show rejection rates far above 5% (≈83–88%), highlighting false correlations.  
- The **Monte Carlo simulation** of Dickey–Fuller statistics accurately reproduces theoretical critical values.  
- The **U.S. GDP (1990–2023)** exhibits a **non-stationary trend**, with unit root confirmed by Dickey–Fuller and contradicted by KPSS tests, depending on the subperiod.

Example visualizations include:
- AR(1) responses to permanent/transitory shocks  
- Deterministic vs. stochastic trend comparisons  
- Empirical distribution of the Dickey–Fuller t-statistic  
- Evolution of U.S. GDP with shaded recession periods

---

## 🧠 References
For theoretical background:
- Hamilton, *Time Series Analysis*  
- Hyndman & Athanasopoulos, *Forecasting: Principles and Practice*  
- Wooldridge, *Introductory Econometrics: A Modern Approach*  
- Sévi, B. (2024). *Support de cours – Séries temporelles univariées (M1 ECAP)*

---

## 📜 License
This project is released under the **MIT License**.  
© 2025 Achille Marteret and Florian Crochet

---

## 👤 Authors
**Achille Marteret**  

**Florian Crochet**  
[GitHub Profile](https://github.com/floriancrochet)

*Master 1 – Econometrics & Statistics, Applied Econometrics Track* 

---

## 💬 Acknowledgments
Thanks to **Benoît Sévi** for the course supervision and to the R open-source community for the tools used throughout this project.
