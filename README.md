# US Treasury Yield Curve: PCA Analysis

What drives the US Treasury yield curve, and how many factors does it take to describe it?

## Summary
I ran a principal component analysis on daily yield changes (3M to 30Y,
2010 to 2026) from FRED. One factor (level) explains 80.1% of daily
movement and three factors explain 95.7%. The three factors correspond
to level, slope and a short-end curvature factor.

## Data
Daily constant-maturity Treasury yields from FRED (series DGS1MO to DGS30).

## Method
- PCA on daily changes in basis points, not yield levels
- Covariance matrix, which keeps the basis-point scale
- The 1M tenor is excluded: it had higher volatility than the 3M and 6M,
  almost no correlation with the long end, and took over PC3 on its own

## Limitations
- One pooled sample period; no regime analysis yet
- In-sample results only
- Dropping the 1M means the analysis covers 3M to 30Y only
- Why the 1M behaves differently is untested

## Next steps
Rolling-window PCA, a PCA-based hedging experiment, and an out-of-sample test.

## How to run
Open `yield_curve_pca.ipynb` in Google Colab and run all cells.
Data is downloaded live from FRED, so results may shift slightly as new days are added.
