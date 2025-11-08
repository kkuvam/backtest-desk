# Backtest-Desk

Backtest-Desk is a small research toolkit for generating rule-based trading signals on Indian equity markets and evaluating them through reproducible backtests. It ingests daily bhavcopy data, computes technical indicators, exports BUY/SELL signals, and measures historical performance with both a custom vectorized engine and the `bt` portfolio framework.

This project began as an experiment in building a minimal quant pipeline end-to-end: data ingestion → signal logic → portfolio evaluation.

## Features

- Automatic download of NSE/BSE bhavcopies
- Rolling-window technical indicators (via `ta`)
- Symbol universe filtered by NIFTY index lists
- Two backtesting paths:
  1. Custom vectorized engine
  2. `bt`-based target-weight engine
- Exports dated signal CSVs for reproducibility
- Equity curves, CAGR, drawdown and trade statistics


## Quick Start

1. Download market data  
   Run `pipeline/runner_nse.py` or `pipeline/runner_bse.py` to populate `data/`.

2. Generate signals  
   Run `notebook/signal_nse.ipynb` to compute indicators and export BUY/SELL signals.

3. Backtest  
   - `notebook/backtest_nse.ipynb` for custom vectorized backtesting  
   - `notebook/backtest_nse_bt.ipynb` for the `bt` framework

## Requirements

Python 3.9+  
pip install pandas numpy matplotlib ta bt tqdm

## Notes

- Signals are generated end-of-day and assumed executed on the next trading day (avoids look-ahead bias).
- This is a research/learning project, not financial advice.
