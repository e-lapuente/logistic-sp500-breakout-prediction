# Predicting Short-Term Market Behavior Using Logistic Regression

This project aims to build a logistic regression model to predict the short-term probability of a stock hitting a new local low within the next five trading days. It leverages a variety of technical indicators commonly used in trading strategies, such as simple moving averages (SMA), Relative Strength Index (RSI), MACD, volume analysis, and candlestick patterns, applied across S&P 500 stocks.

The goal is to scan all S&P 500 stocks to detect potential breakouts based on technical indicators. Breakouts are identified when the low price of a stock is higher during the next five days.

The predictive power of the model is then tested through a simple backtesting strategy.

## Approach
Historical price and volume data is downloaded from Yahoo Finance for all SP500 stocks since 2010.

From this data, a range of technical indicators is computed such as SMA crossovers, RSI conditions, MACD cross signals, price distance from moving averages, and volume surges.

A logistic regression is then trained using the selected features using cross-validation and grid search to optimize precision. On the test set, the model reaches 70% accuracy and 54% precision.

The model is also tested on a simple backtesting strategy: each time the model predicts a local low with a probability higher than 0.6, we simulate entering a long position on the stock and holding it for five trading days, or hitting predefined take profit or stop loss criteria. 
The backtesting results show that 42% of such trades are profitable, with a global average return of 0,2% per trade. Among the positions sold after five days, 77% of them result in a positive result, with 1% return on average. This result suggest that the stop loss condition could be refined.

## Next steps
The strategy could be enhanced by experimenting with more advanced models such as gradient boosting or random forests, which may capture non-linear relationships more effectively. It would also be valuable to benchmark the model against a naive baseline and the overall return of the S&P 500 to better assess its relative performance. Additionally, the backtesting results suggest that refining the stop-loss rule could significantly improve the success rates.

