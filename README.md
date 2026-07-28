# apple-revenue-forecasting-regression
# Apple Revenue Forecasting (Time Series Regression)

A simple time series regression project that forecasts Apple's quarterly revenue using Python.

# What this does

Using ~20 years of quarterly financial data, I built a regression model to forecast Apple's revenue. I started with a basic time-trend model, then improved it by adding a seasonal dummy variable to account for the holiday-quarter iPhone sales bump.

Model 1 - Time trend only:

revenue = -13,536.82 + 1,077.61 * time

Revenue grows by about $1,077 million per quarter on average.

Model 2 - Time trend + iPhone launch quarter:

revenue = -11,044.75 + 933.21 * time - 10,422.13 * iphone_dv + 578.33 * (time * iphone_dv)

This version flags Apple's fiscal Q1 (the December quarter, when new iPhones are on shelves) and lets that quarter have both a revenue jump and its own growth rate, since the holiday bump has gotten bigger over the years.

# Data

`qSales_2024.csv` - quarterly sales data pulled from Compustat, covering Apple, Target, and Nintendo from 2001-2024. Only the Apple rows are used in this analysis.

# Tools

Python, pandas, numpy, statsmodels, matplotlib

# How to run it

1. Open `AFM244_S26_Week11_001_Thursday.ipynb` in Google Colab or Jupyter
2. Make sure `qSales_2024.csv` is in the same folder / uploaded to your session
3. Run all cells top to bottom

The notebook walks through: cleaning the data, visualizing Apple's revenue over time, building the time variable, splitting into training/test sets (75/25), fitting both regression models, and forecasting revenue with confidence intervals.
