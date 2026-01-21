# **Network-Value-Investing**

A quantitative investment framework that combines **Network Science** with **Value Investing**.

## **1. Methodology**

* **Network Science:** Filters market noise using a **Planar Maximally Filtered Graph (PMFG)**. We select "Peripheral" assets—those with the lowest **Node Strength** to minimize systemic risk.
* **Value Investing:** Screens the selected assets for profitability and solvency.

## **2. Notebooks**

1. **`Portfolio_Optimization_with_PMFG_and_Sharpe.ipynb`**: Handles topological filtering, centrality analysis, and robust portfolio weighting (Max Sharpe).
2. **`Value_Investing_Financial_indicators_Tool.ipynb`**: Performs multi-KPI scoring and intrinsic valuation using Benjamin Graham's principles.

## **3. Quick Start**

1. **Selection:** Identify N peripheral stocks via the Network notebook.
2. **Validation:** Run those stocks through the Value tool to filter for high-quality balance sheets.
3. **Optimization:** Use the final intersection to build a diversified, low-contagion portfolio.

## **Dependencies**

`yfinance`, `pandas`, `networkx`, `PyPortfolioOpt`, `requests`, `matplotlib`, `numpy`, `seaborn`

---

**Author:** Cairo Henrique Vaz Cotrim
