# **Portfolio Selection and Optimization Algorithm via Network Theory and Efficient Frontier**

This notebook implements an advanced portfolio construction strategy, utilizing topological graph filtering and centrality metrics to mitigate systemic risk within the stock market.

---

## **1. Selection Methodology**

This algorithm follows three fundamental stages:

### **A. Topological Filtering (PMFG)**

The raw correlation matrix is filtered using the **Planar Maximally Filtered Graph (PMFG)** algorithm. This technique extracts the "skeleton" of the market's strongest connections while maintaining graph planarity. This allows for the identification of sector clusters and essential connections that the raw matrix often obscures.

### **B. Centrality Selection (Investing in the Periphery)**

We use the **Node Strength** (Weighted Degree) metric as a centrality measure in relation to the network. The algorithm selects assets with the **lowest centrality**.

* **Thesis:** "Central" assets (Hubs) carry high systemic risk and tend to collapse together during crises. "Peripheral" assets offer genuine diversification and protection against contagion.

### **C. Robust Optimization**

To avoid excessive concentration, we choose the max Sharpe portfolio via efficient frontier optimization to define final weights.

---

## **2. Notebook Workflow**

1. **Data Ingestion:** Download of B3 tickers via `yfinance`.
2. **Filtering:** Construction of the PMFG graph and noise removal from the correlation matrix.
3. **Network Analysis:** Calculation of centrality metrics and identification of "Core" and "Periphery."
4. **Optimization:** Generation of Maximum Sharpe and Minimum Volatility portfolios.
5. **Backtest:** Comparison of accumulated performance against **IBOVESPA** and **CDI**.

---

## **3. Libraries Used**

* `PyPortfolioOpt`: For Efficient Frontier and HRP calculations.
* `NetworkX`: For construction and topological analysis of the PMFG graph.
* `yfinance`: For obtaining historical data.
* `pandas` & `numpy`: For time-series processing.
* `matplotlib` & `seaborn`: For data and network visualization.
* `requests`: To access the Central Bank (BCB) API.

---

### **How to Use**

1. Execute the dependency installation cells.
2. Define the analysis period in the parameters section.
3. The final graph will display a comparison of R$ 1.00 invested in the strategy versus the benchmarks.
