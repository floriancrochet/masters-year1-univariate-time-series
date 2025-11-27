# ARMA Process Simulation and Stationarity Analysis  
*R-based analysis of ARMA process stationarity and autocorrelation patterns.*

[**Stochastic Processes Report**](https://drive.google.com/file/d/1ermB-n0d533Lh_V_2GMQBygR_mn3Ufyp/view?usp=drive_link)

---

## 📘 Overview
This project presents an academic implementation of **stochastic process simulations and stationarity analysis** using R.  
It was developed as part of the course **“Séries temporelles univariées” (M1 ECAP, 2024–2025)** under the supervision of **Benoît Sévi**.

**Objectives**
- Express ARMA processes using the lag operator \(L\) and determine their characteristic equations.  
- Assess weak stationarity conditions for each process.  
- Simulate and visualize AR, MA, and ARMA processes to analyze **ACF (Autocorrelation Function)** and **PACF (Partial Autocorrelation Function)** patterns.  
- Ensure **clarity, reproducibility, and analytical precision** in time series modeling.

---

## ⚙️ Features
- Analytical study of **ARMA(p,q)** stationarity using characteristic roots.  
- Simulation of stochastic processes with controlled random seeds for reproducibility.  
- Automatic generation of ACF and PACF plots.  
- Use of **ggplot2** and **forecast** for high-quality visualizations.  
- Consistent structure across exercises for methodological transparency.  

---

## 🧰 Tech Stack
**Language:** R  
**Libraries:** `tseries`, `forecast`, `FinTS`, `Metrics`, `TSA`, `ggplot2`, `purrr`  

---

## ⚙️ Installation
To reproduce the analysis, ensure that **R** and **RStudio** are installed, then load the required libraries:

```r
install.packages(c("tseries", "forecast", "FinTS", "Metrics", "TSA", "ggplot2", "purrr"))
```

Open the R Markdown or script file and execute all cells to generate the analysis report in PDF format.

---

## 📚 Usage Example
Example: simulate an AR(1) process \( Y_t = 0.65 Y_{t-1} + 
arepsilon_t \)

```r
set.seed(983)
T <- 1000
epsilon <- rnorm(T)
Y <- ts(numeric(T))
Phi <- 0.65

for (t in 2:T) {
  Y[t] <- Phi * Y[t - 1] + epsilon[t]
}

autoplot(Y)
ggAcf(Y)
ggPacf(Y)
```

These commands reproduce one of the analyses from **Exercise 2**.

---

## 📂 Project Structure

```
TD1_Djayan_Florian/
│
├── code uts 1.txt            # R Markdown code for TD1
├── TD1_Djayan_Florian.pdf    # Rendered PDF report
├── Support1_Series_...pdf    # Course support material
└── README.md                 # Documentation (this file)
```

---

## 📊 Results
The report includes analytical and simulated results for:
- **MA(1), MA(2), AR(1), AR(2), ARMA(1,1), ARMA(3,2)**  
  – Stationarity verified through polynomial roots  
- **Simulations and plots for AR/MA/ARMA processes**  
  – ACF and PACF shapes confirm theoretical expectations:
  - AR processes: exponentially decaying ACF  
  - MA processes: ACF cuts off after lag q  
  - ARMA processes: mixed exponential patterns

---

## 🧠 References
- Hyndman & Athanasopoulos, *Forecasting: Principles and Practice*  
- Hamilton, *Time Series Analysis*  
- Wooldridge, *Introductory Econometrics: A Modern Approach*  
- Sévi, B. (2024–2025). *Séries temporelles univariées – Support de cours M1 ECAP*  

---

## 📜 License
This project is released under the **MIT License**.  
© 2025 Djayan Daëron and Florian Crochet

---

## 👤 Authors
**Djayan Daëron**  
[GitHub Profile](https://github.com/Djayan-D)  

**Florian Crochet**  
[GitHub Profile](https://github.com/floriancrochet)

*Master 1 – Econometrics & Statistics, Applied Econometrics Track*  

---

## 💬 Acknowledgments
This work was completed as part of the **M1 ECAP “Time Series” course**.  
Thanks to the R open-source community and the academic supervision of **Benoît Sévi** for guidance on stochastic process modeling.
