# Market Risk Measurement using VaR and Expected Shortfall

An end-to-end market risk analysis of a multi-asset portfolio using Value at Risk (VaR), Expected Shortfall (ES), Monte Carlo simulation, dynamic volatility modelling, formal model backtesting, and portfolio stress testing.

## Project Overview

This project analyses an equally weighted **$1 million portfolio** consisting of five major asset classes:

| Ticker | Asset | Portfolio Allocation |
|---|---|---:|
| SPY | S&P 500 ETF | $200,000 |
| QQQ | Nasdaq-100 ETF | $200,000 |
| TLT | Long-Duration US Treasury ETF | $200,000 |
| LQD | Investment-Grade Corporate Bond ETF | $200,000 |
| GLD | Gold ETF | $200,000 |
| **Total** | **5 Assets** | **$1,000,000** |

The objective is to evaluate portfolio market risk under normal and extreme market conditions using multiple quantitative approaches.

## Methodology

### 1. Portfolio Risk Analysis
- Portfolio return and volatility analysis
- Asset correlation analysis
- Portfolio drawdown analysis

### 2. Value at Risk (VaR) and Expected Shortfall (ES)
- Historical VaR and Expected Shortfall
- Gaussian parametric VaR and Expected Shortfall
- Monte Carlo simulation

### 3. Volatility and Tail-Risk Modelling
- EWMA volatility modelling
- Student-t distribution for heavy-tailed returns
- Rolling no-look-ahead Student-t EWMA VaR

### 4. VaR Model Backtesting
- Rolling VaR backtesting
- Kupiec unconditional-coverage test
- Christoffersen independence test
- Christoffersen conditional-coverage test

### 5. Portfolio Stress Testing
- Historical market stress scenarios
- Hypothetical market stress scenarios
- Asset-level stress P&L attribution

## Key Findings

- Portfolio returns exhibit heavy tails and volatility clustering, limiting the reliability of Gaussian risk assumptions.
- Historical 99% VaR provides the strongest unconditional calibration among the tested models.
- Gaussian specifications materially underestimate extreme tail risk.
- EWMA improves volatility responsiveness but does not eliminate clustered VaR exceptions.
- Rolling Student-t EWMA improves tail modelling relative to Gaussian EWMA but still fails conditional-coverage testing.
- Diversification benefits can weaken materially when equities and fixed income decline simultaneously.

## Model Validation

VaR models are evaluated using formal statistical backtesting techniques:

| Statistical Test | Purpose |
|---|---|
| Kupiec Unconditional Coverage Test | Tests whether the observed exception frequency matches the expected frequency. |
| Christoffersen Independence Test | Tests whether VaR exceptions occur independently. |
| Christoffersen Conditional Coverage Test | Tests both exception frequency and independence. |

**Validation Conclusion:** No tested specification satisfies all conditional-coverage requirements, highlighting the limitations of relying on a single VaR model for portfolio risk management.

## Stress Testing

The project evaluates both historical and hypothetical market shocks.

### Historical Stress Scenarios
- 2018 Q4 Market Selloff
- COVID-19 Market Crash
- 2022 Cross-Asset Selloff

### Hypothetical Stress Scenarios
- Equity Market Crash
- Interest-Rate Shocks
- Risk-Off Market Environment
- Simultaneous Cross-Asset Declines

Stress testing also evaluates asset-level profit and loss contributions to identify the sources of portfolio losses.

## Technology Stack

- **Programming Language:** Python
- **Data Analysis:** pandas, NumPy
- **Statistical Modelling:** SciPy
- **Data Visualization:** Matplotlib
- **Market Data:** yfinance
- **Development Environment:** Jupyter Notebook

## Repository Structure

```text
market-risk-var-expected-shortfall/
│
├── market_risk_var_expected_shortfall.ipynb
├── README.md
└── requirements.txt
```

## Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/sompartha/market-risk-var-expected-shortfall.git
```

### 2. Navigate to the Project Directory

```bash
cd market-risk-var-expected-shortfall
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Launch Jupyter Notebook

```bash
jupyter notebook
```

Open `market_risk_var_expected_shortfall.ipynb` and execute the analysis.

## Disclaimer

This project is intended solely for educational and portfolio demonstration purposes. It does not constitute investment advice or a recommendation to buy or sell any financial instrument.
