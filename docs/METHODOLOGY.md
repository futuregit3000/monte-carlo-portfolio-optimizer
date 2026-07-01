# Methodology

## Historical estimation

Daily adjusted ETF prices are downloaded and converted into daily returns.
Expected annual return is estimated as mean daily return multiplied by 252.
The annual covariance matrix is the daily covariance matrix multiplied by 252.

## Random portfolio simulation

The project draws 50,000 long-only portfolios from a Dirichlet distribution.
Portfolios exceeding the 35% per-asset cap are rejected.

For weights `w`, annual mean returns `mu`, and annual covariance `Sigma`:

```text
Expected return = w' mu
Variance        = w' Sigma w
Volatility      = sqrt(w' Sigma w)
Sharpe ratio    = (Expected return - Risk-free rate) / Volatility
```

## Constrained optimization

SciPy's SLSQP solver identifies:

- The maximum-Sharpe portfolio
- The minimum-volatility portfolio
- The maximum-return feasible portfolio
- Seventy minimum-volatility portfolios at specified target returns

All portfolios are long-only, fully invested, and capped at 35% per asset.

## Parametric Monte Carlo model

Monthly ETF log returns are modeled with their historical mean vector and
covariance matrix. A Cholesky factor converts independent normal shocks into
correlated asset shocks.

Simulated log returns are converted to simple returns with:

```text
simple return = exp(log return) - 1
```

The portfolio is restored to its target weights at each month-end. Trading
costs are charged on gross traded notional.

## Historical block bootstrap

The bootstrap resamples six-month blocks of actual monthly cross-asset returns.
This preserves same-month cross-asset relationships and some short-run temporal
dependence without imposing a normal distribution.

## Stress testing

The stress system blends the historical correlation matrix toward a matrix of
perfect positive correlation. A recession scenario also subtracts 0.50% per
month from the expected log returns of risky assets.

## Allocation and horizon surface

Equity and real-estate allocation varies from 0% to 100%. The remaining
allocation is divided equally among Treasuries, corporate bonds, gold, and
Treasury bills. The project measures the probability of finishing below
initial capital over horizons from one to ten years.
