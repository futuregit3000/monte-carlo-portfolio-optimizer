# Limitations and Interpretation

## Expected-return uncertainty

Expected returns are much harder to estimate than volatility and correlation.
Small changes in estimated returns can materially change optimized weights.

## Concentrated optimizer solutions

The maximum-Sharpe solution reaches the 35% cap in QQQ and places large weights
in BIL and GLD. This is a historical mathematical solution, not a recommended
portfolio.

## Distribution assumptions

The main Monte Carlo model assumes multivariate normal monthly log returns.
Real markets can exhibit skewness, fat tails, volatility clustering, jumps,
liquidity shocks, and changing correlations.

## Bootstrap limitations

The block bootstrap avoids the normal-distribution assumption, but it cannot
simulate events or structural regimes absent from the historical sample.

## Data and universe selection

The ETF universe and sample period were selected using present-day knowledge.
Yahoo Finance data is suitable for education but not equivalent to an
institutional total-return database.

## Execution simplifications

The model uses monthly rebalancing and a fixed five-basis-point cost. It does
not fully model bid-ask spreads, taxes, market impact, fund tracking error, or
execution timing.

## Interpreting the zero simulated loss rate

None of the 10,000 parametric ten-year paths finished below the initial
$100,000 under the estimated model. This is a finite simulation result—not a
claim that the true probability of loss is zero.

## No genuine out-of-sample test

The same broad historical sample informs model design, parameter estimation,
and evaluation. A stronger future version would freeze the methodology on a
training period and evaluate it once on untouched later data.
