# Data Sources and Technical References

## Market data

- Yahoo Finance market data accessed through `yfinance`
- yfinance documentation: https://ranaroussi.github.io/yfinance/

Yahoo Finance data is appropriate for educational research, but it is not an
institutional market-data feed and may contain revisions, gaps, or vendor
adjustments.

## Risk-free rate

- FRED three-month Treasury series: DGS3MO
- Federal Reserve Bank of St. Louis: https://fred.stlouisfed.org/series/DGS3MO
- pandas-datareader FRED interface:
  https://pandas-datareader.readthedocs.io/

## Numerical methods

- SciPy optimization documentation:
  https://docs.scipy.org/doc/scipy/reference/optimize.html
- NumPy linear algebra documentation:
  https://numpy.org/doc/stable/reference/routines.linalg.html

## Research note

The project uses historical estimates, constrained mean-variance optimization,
correlated parametric simulation, and historical block bootstrapping. Results
are model-dependent and do not constitute investment advice.
