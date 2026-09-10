# MGNM801 – TCS Stock Price Analytics

## Business Analytics Using Python

### Descriptive and Predictive Analysis of TCS Stock Prices

This project presents a data-driven analysis of Tata Consultancy Services (TCS) stock prices using Python. The analysis focuses on historical price trends, trading volume, daily returns, moving averages, volatility, and prediction of the next trading day's closing price.

## 1. Business Problem

The objective of this project is to analyze TCS stock-price and trading-volume data to identify important trends, relationships, and volatility patterns. The project also evaluates whether current-day market information can be used to estimate the next trading day's closing price.

## 2. Objectives

- Analyze historical TCS stock-price and trading-volume data.
- Identify major trends and patterns in closing prices.
- Examine the relationship between closing price and trading volume.
- Analyze daily returns, moving averages, and rolling volatility.
- Develop and evaluate predictive models for next-day closing price.
- Compare predictive models using MAE, RMSE, and R².
- Generate business insights and actionable recommendations.

## 3. Data Source

**Source:** Yahoo Finance  
**Ticker:** TCS.NS  
**Frequency:** Daily  
**Data Period:** 8 September 2021 to 7 September 2026  
**Initial Observations:** 1,240  
**Cleaned Observations:** 1,239

The dataset contains market variables including Open, High, Low, Close, Adjusted Close, and Volume.

## 4. Data Preparation

The data was collected using the `yfinance` Python library.

The following preparation steps were performed:

- Checked for missing values.
- Checked for duplicate records.
- Converted dates into the appropriate date format.
- Sorted observations chronologically.
- Handled the dataset structure returned by Yahoo Finance.
- Ensured numerical variables had appropriate data types.
- Created additional analytical features.
- Created the next-day closing price as the prediction target.

### Engineered Features

- Daily Return
- 7-Day Moving Average (MA_7)
- 21-Day Moving Average (MA_21)
- 21-Day Rolling Volatility
- Previous Close
- Next Day Close

## 5. Descriptive Analytics

The project examines:

- Historical closing-price trends
- Trading-volume trends
- Daily-return distribution
- Closing price and trading-volume relationship
- Monthly average closing prices
- 7-day and 21-day moving averages
- 21-day rolling volatility

### Key Descriptive Results

| Measure | Result |
|---|---:|
| Average Closing Price | ₹3,415.61 |
| Minimum Closing Price | ₹1,982.60 |
| Maximum Closing Price | ₹4,553.75 |
| Average Daily Return | -0.03% |
| Average Trading Volume | 2,607,623 shares |
| Average 21-Day Volatility | 1.36% |
| Close-Volume Correlation | -0.286 |

## 6. Predictive Analytics

### Target Variable

**Next_Day_Close**

### Predictors

- Open
- High
- Low
- Close
- Volume
- Daily Return
- MA_7
- MA_21
- Volatility_21
- Previous Close

A chronological 80:20 train-test split was used to avoid randomly mixing past and future observations.

- Training observations: 973
- Testing observations: 244

### Models Evaluated

1. Baseline Model – Today's Closing Price
2. Linear Regression
3. Random Forest Regression

## 7. Model Evaluation

| Model | MAE | RMSE | R² |
|---|---:|---:|---:|
| Baseline | ₹32.59 | ₹45.94 | 0.9869 |
| Linear Regression | ₹35.32 | ₹48.42 | 0.9855 |
| Random Forest | ₹434.71 | ₹560.12 | -0.9472 |

The baseline model produced the best performance on the test data, followed closely by Linear Regression. Random Forest performed substantially worse on the test period.

## 8. Final Prediction

The latest complete trading observation used for the final prediction was **4 September 2026**.

- Latest closing price: **₹2,304**
- Selected approach: **Baseline – Today's Closing Price**
- Predicted next trading day closing price: **₹2,304**
- Expected change: **₹0 (0%)**

## 9. Key Findings

- TCS closing prices experienced different market phases over the study period.
- The later part of the dataset showed a pronounced decline in closing prices.
- Trading volume did not show a strong positive relationship with closing price.
- Daily returns were generally small, with occasional larger movements.
- Moving averages helped identify short- and medium-term price trends.
- Higher rolling volatility indicated periods of greater uncertainty.
- The baseline model outperformed the more complex models for this particular test period.
- Random Forest showed difficulty adapting to the changing price regime.

## 10. Business Recommendations

1. Use simple benchmark models alongside advanced machine-learning models.
2. Monitor rolling volatility when assessing market risk and uncertainty.
3. Do not rely on trading volume alone when interpreting stock-price movements.
4. Regularly update predictive models as new market data becomes available.
5. Use predictive models as decision-support tools rather than as guaranteed forecasts.

## 11. Tools and Technologies

- Python
- Google Colab
- Pandas
- NumPy
- Matplotlib
- Scikit-learn
- yfinance

## 12. Project Notebook

The complete Python implementation, analysis, visualizations, model evaluation, and outputs are available in the Jupyter Notebook included in this repository.

The notebook can also be opened directly in Google Colab using the Colab link provided in the notebook.

## 13. Conclusion

This project demonstrates how Python-based business analytics can be applied to real-world financial data. The analysis combines descriptive analytics, visualization, feature engineering, and predictive modelling to generate insights into TCS stock-price behaviour and next-day price prediction.
