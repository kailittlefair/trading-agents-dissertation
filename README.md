# A Comparative Study of Learning and Heuristic Decision Agents on Historical Financial Time Series

**Kai John Littlefair**  
MSc Advanced Computer Science (Artificial Intelligence)  
University of Leeds, School of Computer Science  
2025/2026

## Project Overview

This repository contains the code developed for my MSc dissertation. The project implements and evaluates five autonomous decision-making agents operating on historical S&P 500 daily price data, comparing a Q-learning reinforcement learning agent against four heuristic trading strategies under identical conditions.

The five agents are:
- **Random Agent** — lower-bound baseline
- **Moving Average Crossover Agent** — trend-following using golden/death cross signals
- **Momentum Agent** — enters on sustained 20-day positive momentum
- **Mean Reversion Agent** — enters when price deviates significantly below its rolling mean
- **Q-Learning (RL) Agent** — learns a trading policy through interaction with historical data

## Requirements

The notebook runs in Google Colab which require no local setup. If running locally, install dependencies with:

```bash
pip install numpy pandas matplotlib yfinance scipy
```

## How to Run

1. Open `MSc_Project_Notebook.ipynb` in [Google Colab](https://colab.research.google.com)
2. Run all cells in order (**Runtime → Run all**)
3. The notebook downloads S&P 500 data automatically via Yahoo Finance

**Important:** All cells must be run sequentially from top to bottom. Later cells depend on variables defined in earlier ones.

## Key Results

Evaluated on an out-of-sample window of 752 trading days (late 2022 to March 2026):

| Agent | Cumulative Return | Sharpe Ratio |
|-------|------------------|--------------|
| Q-Learning (RL) | 142.57% | 2.64 |
| Momentum | 59.88% | 1.75 |
| Moving Average | 41.28% | 1.26 |
| Buy & Hold | 73.09% | 1.31 |
| Mean Reversion | -23.46% | -0.78 |
| Random | -3.37% | -0.06 |

Note: The Q-Learning agent's performance should be interpreted as a distribution across training seeds (mean cumulative return 128.72%, std 38.64%) rather than as a single point estimate.
