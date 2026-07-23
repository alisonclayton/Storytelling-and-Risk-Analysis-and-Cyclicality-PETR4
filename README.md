# 📈 Statistical Analysis of Cyclicality and Operational Risk (PETR4)

## [LINK TO THE ENTIRE ANALYSIS](https://github.com/alisonclayton/Storytelling-and-Risk-Analysis-and-Cyclicality-PETR4/blob/bb98273eae16a6cc75f26fc5c46b049f461dc000/Storytelling_and_Risk_Analysis_and_Cyclicality_PETR4.ipynb)

## 📌 Strategic Context and Business Problem

In the Corporate Finance and M&A ecosystem, evaluating a company's efficiency based on the profit of a single fiscal year is a severe methodological flaw. Cyclical companies exposed to global commodities frequently experience profitability peaks followed by severe margin compressions. 

Projecting a company's *Valuation* (DCF) using the cycle's historical ceiling generates an **Analytical Overfitting**, pricing in an unsustainable long-term scenario.

---

## 🎯 Project Objective

The objective of this quantitative essay is to isolate a primary cash generation metric — **EBIT (Earnings Before Interest and Taxes)** and **Operating Margin** — of Petrobras (PETR4) over a consolidated historical cycle. 

Through descriptive statistics, the algorithm purges short-term noise and extracts the company's true "risk signature" and volatility, providing the empirical parameters necessary to support stress tests in advanced pricing models.

---

## 📐 Metrics Engineering: The Statistical Engine

To avoid the myopia of absolute metrics, the algorithmic engine of this repository was architected to process four fundamental pillars of risk and efficiency:

### Historical Average Margin ($\mu$)
The Historical Average Margin ($\mu$) acts as the "waterline" of the company's operational efficiency, purging exogenous noises and extreme short-term fluctuations. By observing a complete cycle, this metric extracts the company's true structural cash generation power, ignoring the temporary supply and demand shocks inherent to the commodities market.

From a *Valuation* perspective, the average is the primary anchoring parameter for Discounted Cash Flow (DCF) projections. Using it as a stability premise ensures that the corporate financial model is not contaminated by the false hope of continuous record profits, shielding the investment thesis and the decision-making of top management.

Mathematically, the arithmetic mean ($\mu$) is calculated by the sum of all operating margins ($x_i$) recorded in each period of the cycle, divided by the total number of observations ($N$). The equation underlying this metric is expressed by: 
$$\mu = \frac{1}{N} \sum_{i=1}^{N} x_i$$

### Volatility and Absolute Risk ($\sigma$)
The Standard Deviation ($\sigma$) quantifies the absolute risk of the business, measuring the mathematical dispersion of annual results relative to their own historical average. To ensure algorithmic rigor and precision in this essay, the statistical engine in the `numpy` library was calibrated using the population standard deviation, treating the financial *dataset* not as a partial sample, but as the reflection of a consolidated cycle.

In market practice, high volatility indicates highly unpredictable cash flows susceptible to macroeconomic adversities. Understanding the exact magnitude of this dispersion is fundamental for the Investor Relations (IR) area and the *Sell-Side*, as it translates the intrinsic uncertainty of the company's cost infrastructure into irrefutable and auditable numbers.

From an algebraic perspective, the Population Standard Deviation ($\sigma$) is the square root of the variance. It calculates the difference (distance) of each individual margin ($x_i$) from the mean ($\mu$), squares this result (to prevent negative values from canceling out positive ones), and divides by the total number of observations ($N$). The formula applied in the processing is: 
$$\sigma = \sqrt{\frac{1}{N} \sum_{i=1}^{N} (x_i - \mu)^2}$$

### Coefficient of Variation (CV)
The Coefficient of Variation is the definitive relative risk metric of this project, extracted directly from the mathematical ratio between Volatility and the Average Margin ($\sigma / \mu$). While the standard deviation delivers a static value that makes benchmarking between corporations in different sectors difficult, the CV standardizes the risk into a percentage format or a universal scale multiplier.

A high CV — such as limits crossing the 30% barrier in severely cyclical operations — triggers red alerts of systemic instability. This reading imposes a rigorous penalty on capital structuring, requiring shareholders to embed a substantially higher risk premium in the Weighted Average Cost of Capital (WACC) to justify maintaining investments.

The calculation of the Coefficient of Variation is a simple yet powerful operation, defined by the direct ratio between the Standard Deviation ($\sigma$) and the Average Margin ($\mu$). Because it is a division of absolute risk by baseline profitability, the result is a dimensionless number (often read as a percentage or in times, "x") expressed by the equation: 
$$CV = \frac{\sigma}{\mu}$$

### Stress Limits (Min/Max)
The extreme parameters of the data vector operate as the mandatory boundaries for the execution of *Stress Testing*. The Historical Ceiling (Max) exposes the profitability peak generated by perfect and frequently anomalous market alignments, while the Historical Floor (Min) meticulously maps the worst scenario of margin crushing ever experienced and supported by the operational structure.

The technical governance of this repository determines that projecting perpetual flows based on the Ceiling is an amateur modeling error. Conversely, the mapping of the Floor is the most aggressive tool for mitigating *Tail Risk*, establishing the minimum support limit to validate the viability of leverage or the approval of new projects in the company's portfolio.

In the field of set theory and real analysis, stress limits correspond to the extreme values contained in the data vector $X$, where $X = \{x_1, x_2, \dots, x_N\}$. The algorithm executes a scan function to isolate the lowest and highest recorded margins, mathematically defining the tail scenarios through: 
$$\text{Min} = \min(X) \quad \text{and} \quad \text{Max} = \max(X)$$

---

## 🛠️ Tech Stack and Methodology
* **Language:** Python 3
* **Environment:** Google Colab / Jupyter Notebook
* **Libraries:** `pandas` (Pipeline and Data Ingestion) and `numpy` (High-Performance Statistical Processing)
* **Visual Rendering:** Dynamic HTML/CSS encapsulated via `IPython.display` to simulate *Big Numbers* and native BI cards in the console.

---

## 📊 Data Storytelling (Summary of Findings)
The data architecture processed in this repository numerically proves that, despite the impressive efficiency leap recorded at the cycle's peak (such as the one that occurred in 2022), the operation carries a **Coefficient of Variation exceeding 30%**. 

*In casu*, it is a business model of extremely high cyclicality and difficult anchoring. The fiduciary and technical recommendation generated by the model points out that future *Valuation* assumptions must rigorously converge to the Historical Average of the margin, using the Historical Floor (*Stress Test*) to protect cash flow against severe exogenous shocks.

---

## 🚀 Repository Structure and How to Run
All the rationale behind the metrics, the cleaning pipeline for dirty CSV variables, and the statistical engine in Python are documented linearly in the interactive environment.

1. Access the primary analysis *notebook*: [https://github.com/alisonclayton/Storytelling-and-Risk-Analysis-and-Cyclicality-PETR4](#).
2. Ensure you upload the historical dataset (`.csv`) to the same root directory of the execution environment.
3. The document interleaves the *Business Storytelling* with executable blocks (*E2E Analysis*), replicating a C-Level *dashboard* directly in standard Python output.
