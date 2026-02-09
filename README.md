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
