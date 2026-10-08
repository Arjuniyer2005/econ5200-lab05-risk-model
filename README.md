# econ5200-lab05-risk-model
# Diagnosing a Flawed Risk Model — VaR, Expected Shortfall & Monte Carlo

## Objective
I evaluated a portfolio risk model to identify weaknesses in its assumptions and compare alternative methods for estimating potential losses.

## Methodology
- Analyzed 2,520 daily portfolio returns and examined their distribution, skewness, and excess kurtosis.
- Compared 95% and 99% Value at Risk (VaR) estimates using normal and historical distributions.
- Calculated 99% VaR and Expected Shortfall (ES) using normal, historical, and fitted Student-t distributions.
- Used antithetic variates to reduce Monte Carlo simulation error and compared the results against the Black-Scholes option price.
- Ran the `risk_metrics.py` module and tested its `calculate_var()`, `calculate_es()`, and `mc_var()` functions.
- Used AI to generate a VaR backtesting function, revised my prompt to clarify its assumptions, and checked the results against my own calculations.

## Key Findings
- The normal distribution underestimated historical 99% VaR by 12.7%, equivalent to $40,393 on a $10 million portfolio.
- The return distribution had an excess kurtosis of 4.28, indicating heavier tails than a normal distribution.
- The Student-t distribution better accounted for extreme returns, while Expected Shortfall captured the average severity of losses beyond VaR.
- Antithetic variates reduced Monte Carlo standard error by a factor of 1.26 without increasing the number of simulations.
- The backtest showed that normal VaR was breached more frequently than its expected 1% rate, confirming that the analyst's model underestimated extreme downside risk.

## Conclusion
This lab showed me that a model can produce mathematically correct results while still giving misleading estimates because of its assumptions. Comparing different risk measures and checking model predictions against actual returns helped identify the problem.
