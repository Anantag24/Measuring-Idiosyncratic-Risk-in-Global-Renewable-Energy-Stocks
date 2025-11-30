📘 **Measuring Idiosyncratic Risk in Global Renewable Energy Stocks**

This repository contains the full workflow, code, data, and results for the project:

**“Measuring Idiosyncratic Risk in Global Renewable Energy Stocks”**

The study evaluates idiosyncratic risk in renewable-energy companies using multi-factor asset-pricing models, risk decomposition techniques, and regression-based approaches including the **Fama–French 3-Factor Model**, **Fama–MacBeth regressions**, and **GARCH-type volatility modeling**.

 🚀 **Project Highlights**

* Constructed **clean daily returns**, **market cap–based SMB**, and **book-to-market HML** factors.
* Estimated **idiosyncratic volatility** using:

  * FF3 regression residuals
  * Rolling 30-day variance
  * EGARCH(1,1) model
* Conducted full **Fama–MacBeth cross-sectional regressions** to test risk-return relationships.
* Compared volatility patterns across oil, renewable, and broad-market sectors.
* Produced a final **summary report** consolidating results and insights.


🧠 **Methodology Overview**

**1️⃣ Data Preparation**

* Downloaded daily price data for global renewable-energy stocks.
* Cleaned and aligned datasets, filled missing values, standardized time index.
* Constructed:

  * Market return (MKT)
  * SMB (size factor)
  * HML (value factor)
  * Risk-free rate


**2️⃣ FF3 Time-Series Regression**

For each stock:

[
R_{it} - R_f = \alpha_i + \beta_{MKT} MKT_t + \beta_{SMB} SMB_t + \beta_{HML} HML_t + \epsilon_{it}
]

* Extracted **residual variance** → idiosyncratic volatility
* Evaluated factor exposures (market, size, value)

---

**3️⃣ Fama–MacBeth Cross-Sectional Regression**

[
R_i = \lambda_0 + \lambda_1 \beta_{MKT,i} + \lambda_2 \beta_{SMB,i} + \lambda_3 \beta_{HML,i} + \epsilon_i
]

Used to test whether:

* higher factor betas → higher expected return
* idiosyncratic risk is priced in the cross-section

**4️⃣ GARCH / EGARCH Volatility Modeling**

Model used:

[
\ln(\sigma_t^2) = \omega + \alpha \left|\frac{\epsilon_{t-1}}{\sigma_{t-1}}\right| +
\gamma \frac{\epsilon_{t-1}}{\sigma_{t-1}} + \beta \ln(\sigma_{t-1}^2)
]

* Captures asymmetric shocks
* Generates smoothed volatility estimates for comparison

📊 **Key Findings (Short Summary)**

* Renewable-energy stocks show **higher idiosyncratic volatility** than most traditional sectors.
* FF3 factors explain a significant portion of return variation, but **α (alpha) remains large**, indicating pricing inefficiencies.
* Fama–MacBeth results suggest **idiosyncratic volatility is NOT significantly priced**, consistent with academic literature.
* EGARCH models reveal strong **volatility clustering**, especially around geopolitical events and oil price shocks.

🛠️ **How to Run the Project**

**Requirements**

```
Python 3.10+
pandas
numpy
statsmodels
arch
matplotlib
yfinance

**Execute Notebook**

Open:

code/idiosynchratic_code.ipynb

Run cells sequentially:

1. Load & clean data
2. Construct factors
3. Run FF3 regressions
4. Estimate idiosyncratic volatility
5. Run EGARCH
6. Save results → `result/` folder

📄 **Report**

Full explanation, tables, and findings:

report/Summary_report.pdf



🧑‍💻 **Author**

**Ananta Gupta**
*Supervised by:* **Prof. Wasim Ahmed**, IIT Kanpur
Project: *Measuring Idiosyncratic Risk in Global Renewable Energy Stocks*


