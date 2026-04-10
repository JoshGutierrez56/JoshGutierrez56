# Josh Gutierrez

**MS Finance / MBA Candidate, Northeastern University · Boston**  
Quantitative research at the intersection of systematic equity, factor investing, and alternative data.

Currently a student portfolio manager at the [360 Huntington Fund](https://360hf.org) — a student-managed long-equity fund benchmarked against the Russell 3000 — and a quantitative analyst at AEW Capital Management, where I build data-driven valuation and signal models for private real estate portfolios.

My research focus is on the full systematic equity stack: **signal construction → covariance estimation → portfolio optimization → performance attribution**. All repos below are research-grade implementations, tested against real data where possible and against synthetic data with documented assumptions where not.

---

## Repositories

### Systematic Equity

| Repo | What it does |
|---|---|
| [ETF-Deep-Momentum-Network](https://github.com/JoshGutierrez56/ETF-Deep-Momentum-Network) | PyTorch LSTM trained directly on Sharpe ratio. Walk-forward Sharpe 1.65 across 23 ETFs, 28 test periods (2010–2024). |
| [equity-factor-model](https://github.com/JoshGutierrez56/equity-factor-model) | Cross-sectional 5-factor model (MOM, LV, SIZE, VAL, QUAL). Spearman IC analysis with Bonferroni correction, CVXPY factor-constrained optimizer, Brinson attribution. |
| [statistical-arbitrage](https://github.com/JoshGutierrez56/statistical-arbitrage) | Engle-Granger cointegration pair selection, Kalman filter dynamic hedge ratio, OU process parameter estimation, z-score signal with entry/exit/stop logic. |
| [garch-volatility](https://github.com/JoshGutierrez56/garch-volatility) | GARCH(1,1), GJR-GARCH, EGARCH from-scratch MLE (no `arch` library). HAR-RV with daily/weekly/monthly components. Walk-forward QLIKE evaluation. Kupiec VaR backtest. |

### Portfolio Construction & Attribution

| Repo | What it does |
|---|---|
| [risk-parity-sql](https://github.com/JoshGutierrez56/risk-parity-sql) | ERC optimizer (Edward Qian / PanAgora framework). Rolling covariance, NAV, drawdown, and Sharpe entirely in DuckDB SQL window functions. Python only for iterative ERC solve. |
| [360hf-bl-optimizer](https://github.com/JoshGutierrez56/360hf-bl-optimizer) | Black-Litterman FF6 optimizer for the 360 Huntington Fund. FF6 equilibrium as prior, GK analyst signals as views via P/Q/Ω. Replaces Excel Solver with CVXPY. Brinson-Fachler sector + FF6 factor attribution. |

### Alternative Data & NLP

| Repo | What it does |
|---|---|
| [sec-edgar-nlp](https://github.com/JoshGutierrez56/sec-edgar-nlp) | Loughran-McDonald tone, uncertainty, Fog index, and YoY TF-IDF text change from 10-K MD&A sections. Zero API key — uses SEC's free `data.sec.gov` REST API. Spearman IC vs forward returns. |
| [DeepSeek-Generative-AI-Sentiment-Analysis-Algorithm](https://github.com/JoshGutierrez56/DeepSeek-Generative-AI-Sentiment-Analysis-Algorithm) | LLM-driven news sentiment trader. Sliding-window rate limiter, geometric return metrics, fully mocked test suite. |

### Real Estate (AEW Research)

| Repo | What it does |
|---|---|
| [Relative-Value-Index](https://github.com/JoshGutierrez56/Relative-Value-Index) | Open-data replication of the AEW Relative Value Index. Gordon Growth Model sector scoring across NCREIF NPI cap rates, NOI growth momentum, FRED macro data. BL posterior → CVXPY optimizer. |
| [Cap-Rate-Decomposition](https://github.com/JoshGutierrez56/Cap-Rate-Decomposition) | Decomposes NCREIF cap rates into RF + risk premium − NOI growth. OLS, ECM, and ensemble NOI growth models. Bull/Base/Bear scenario valuation. |
| [PERE-Alternative-Data-Signals](https://github.com/JoshGutierrez56/PERE-Alternative-Data-Signals) | Granger-causality tests: public REIT prices, Zillow ZORI, and FRED signals as leading indicators of NCREIF NPI. Replicates AEW's finding of ~0.80 lag-2Q REIT–private RE correlation. |
| [REIT-PERE-Allocation-Optimizer](https://github.com/JoshGutierrez56/REIT-PERE-Allocation-Optimizer) | Mean-variance optimizer for REIT / private RE allocation. Geltner unsmoothing, Ledoit-Wolf shrinkage, CVXPY, macro regime conditioning. |

---

## Stack

```
Python  ·  PyTorch  ·  scipy  ·  CVXPY  ·  numpy  ·  pandas
DuckDB  ·  SQL  ·  openpyxl  ·  yfinance  ·  BeautifulSoup
```

**Methods:** Fama-French factor models · Black-Litterman · Grinold-Kahn · GARCH family · Kalman filter · Engle-Granger cointegration · Loughran-McDonald NLP · Brinson-Fachler attribution · Ledoit-Wolf covariance shrinkage

---

*All implementations are research-grade with documented assumptions, walk-forward evaluation, and unit test suites. Synthetic fallbacks included where live data requires API access.*
