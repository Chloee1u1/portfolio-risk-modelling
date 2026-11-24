# Portfolio Risk Modelling Using ARMA-GARCH and Copula Models

This project analyses the joint behaviour of the S&P 500 and CAC 40 equity indices and estimates portfolio risk using time-series and copula-based methods.

## Overview

The report uses weekly closing prices from 1 January 2000 to 31 December 2025 to construct an equally weighted portfolio of the two indices. The analysis includes:

- Data preparation and calculation of weekly log returns
- Exploratory plots and diagnostics for volatility clustering
- Box–Jenkins identification and comparison of AR(1)-GARCH(1,1) models
- Assessment of conditional distributions using residual diagnostics
- Probability Integral Transform (PIT), with Kolmogorov–Smirnov and Anderson–Darling tests
- Copula selection and Monte Carlo simulation of joint returns
- Reintroduction of time-series effects into simulated returns
- Estimation of one-week portfolio Value-at-Risk (VaR)

The report selects Student-t conditional distributions for the marginal AR(1)-GARCH(1,1) models and uses a t-copula to represent dependence between the indices.

## Main result

The report estimates one-week portfolio VaR at:

| Confidence level | Estimated VaR |
| --- | ---: |
| 95% | 2.28% |
| 99% | 3.83% |

These are the figures reported by the project; see the R Markdown report for the modelling procedure and interpretation.

## Repository contents

- `portfolio_risk_modelling.Rmd` — the R Markdown source report.

## Data requirement

The report reads a CSV file named `S&P500_CAC40.csv`. This input data file is **not included** in this repository, so it must be obtained separately and placed in the R working directory before running the analysis.

The CSV is expected to contain the date, S&P 500, and CAC 40 closing-price columns used in the report.

## R packages

The report uses the following R packages:

- `tidyverse`
- `VineCopula`
- `fGarch`
- `KScorrect`
- `ADGofTest`
- `fBasics`
- `kableExtra`
- `pacman`
- `knitr`
- `rmarkdown`

## Running the report

1. Install the required R packages.
2. Place `S&P500_CAC40.csv` in the working directory.
3. Open `portfolio_risk_modelling.Rmd` in RStudio or another R Markdown-compatible environment.
4. Knit the report to PDF or HTML.
