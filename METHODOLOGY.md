# Methodology and interpretation notes

## Study design

The original study used daily Shanghai Composite Index observations from 5 January 2015 to 7 May 2025. Features included price, volume and technical indicators such as moving averages, RSI and MACD. Correlation analysis was used to inspect multicollinearity before model comparison.

The comparison covered linear, Lasso, Ridge, polynomial, spline, autoregressive (AR) and autoregressive-with-exogenous-variables (ARX) specifications. The original workflow used an 80/20 split for the regression comparison and evaluated models with mean squared error (MSE) and coefficient of determination (R²).

## Reproducibility scope

`notebooks/original_analysis.ipynb` preserves the project's original analytical workflow. Only public-facing hygiene changes were made: the input path was adapted to the repository structure and machine-specific warning output was removed. Model logic was not rewritten.

The metrics in `outputs/model_metrics.csv` reproduce the final comparison table used in the project report. Because the notebook contains exploratory cells and multiple intermediate specifications, isolated cell outputs may differ from the final table.

## Interpretation limits

- The reported metrics describe the original academic comparison; they are not audited live-trading results.
- A high R² for an index-level model does not by itself demonstrate profitable or robust trading performance.
- The original preprocessing and split design should not be treated as a production-grade time-series validation protocol.
- Future work should use chronological walk-forward validation, fit preprocessing only on each training window, and compare against naive forecasting baselines.

This repository is for academic and portfolio presentation only and is not investment advice.
