> **⚠️ Archivist Note:** This repository serves as a sandbox for my early experiments in Quantitative Finance (2025).
> It focuses on the raw implementation of financial metrics (Sharpe, Sortino) and Monte Carlo engines without relying on high-level abstraction libraries.
>
> **Note on Language:** As these were initial study scripts, variable names and inline comments are in **Portuguese** (e.g., `preço_atual` = `current_price`).
> For my production-standard engineering work, please refer to: **[statistical-arbitrage-kalman](github.com/DuarteAbracos/statistical-arbitrage-kalman)**.

### 📖 Code Glossary (PT -> EN)
Since the source code uses Portuguese semantics, here is a mapping for international reviewers:

| Variable (PT) | Meaning (EN) | Context |
| :--- | :--- | :--- |
| `preço_atual` | `current_price` | The last observed closing price |
| `retorno` | `return` | Daily log-returns or percentage change |
| `retornos_negativos` | `negative_returns` | Subset of returns < 0 (used for Sortino) |
| `dias_simulacao` | `simulation_days` | Time horizon for Monte Carlo (e.g., 252 days) |
| `num_cenarios` | `num_scenarios` | Number of random paths generated (e.g., 1000) |


# Quantitative Portfolio Optimization: Sharpe vs. Sortino

## Overview
This repository contains a comparative analysis of risk-adjusted return metrics using **Monte Carlo simulations**. The core objective is to demonstrate the limitations of the Sharpe Ratio in identifying optimal portfolios when return distributions possess positive skewness (upside volatility).

## Key Components

### 1. `simulation.ipynb` (Monte Carlo Engine)
- **Methodology:** Simulates 10,000+ portfolio combinations based on historical asset returns.
- **Efficient Frontier:** Visualizes the risk-return trade-off.
- **Math:** Utilizes Vectorized NumPy operations for high-performance simulation of covariance matrices.

### 2. `metrics.ipynb` (Risk Analytics)
- **Sharpe Ratio:** Traditional mean-variance optimization.
- **Sortino Ratio:** Focuses purely on downside deviation, penalizing only harmful volatility.
- **Key Insight:** In the analysis, the Sortino-optimized portfolio allocated significantly more to [Asset Name/Type] compared to the Sharpe portfolio, proving its effectiveness for assets with high upside potential (e.g., Crypto/Tech stocks).

## Tech Stack
- **Python:** Pandas, NumPy
- **Visualization:** Matplotlib, Seaborn
- **Data Source:** Yahoo Finance API (`yfinance`)

## Future Improvements
- [ ] Implement Black-Litterman model to incorporate subjective views into the optimization.
- [ ] Add "Maximum Drawdown" constraint to the optimization solver.
