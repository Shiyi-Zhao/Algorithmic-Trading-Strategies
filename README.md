# Algorithmic-Trading-Strategies


## Introduction:

This code describes how to create and run an algorithmic trading system that is intended to execute trades using technical analysis, with Bollinger Bands serving as the main indicator. The technique uses paper trading on the Alpaca platform to mimic real-world trading without putting money at risk.

## Market Data Retrieval:

This code retrieves market data from Alpaca by using the ‘alpaca_trade_api’, a Python library that interfaces with the Alpaca API. 

Historical data for a specified symbol is fetched using the ‘get_bars’ method, which returns Open, High, Low, Close, and Volume (OHLCV) data. The system uses this data to calculate technical indicators and make trading decisions.

Additionally, the system fetches the latest market data at predetermined intervals to maintain up-to-date information for real-time decision-making.


## Data Storage Strategy:

The system saves market data to CSV files for persistence and later analysis. Data is appended to existing files if they exist; otherwise, new files are created. This approach allows for easy data retrieval and manipulation using standard data analysis tools.


In the trading system, latest stock data would be saved to a dataframe. If the length of the dataframe is larger than 10000 rows, the dataframe would be saved to the database. Then we create a new dataframe.


## Trading Strategy Development:

The trading strategy is based on Bollinger Bands, a type of statistical chart characterizing the prices and volatility of a financial instrument over time. The strategy generates buy signals when the price closes below the lower band and sell signals when the price closes above the upper band.


Trading instruments: ‘SPY’, which is the SPDR® S&P 500® ETF Trust. It seeks to provide investment results that, before expenses, correspond generally to the price and yield performance of the S&P 500® Index (the “Index”). The S&P 500 Index is a diversified large cap U.S. index that holds companies across all eleven GICS sectors. Launched in January 1993, SPY was the very first exchange traded fund listed in the United States.


## Code Explanation:

Key components of the system include the retrieval of market data(function:get_historical_data, get_latest_data), calculation of technical indicators(function: add_technical_indicators), execution of trades based on signals(function: trading_strategy_BollingerBands), and continuous monitoring and logging of trading activity. The system employs a loop to regularly update market data and evaluate new trading opportunities.

## Testing and Optimization:

The strategy was backtested using historical market data spanning a year to evaluate its performance and optimize parameters. Adjustments were made based on the backtest results to refine the strategy and improve its risk-reward profile.
Tested to have a better return.: 
Bollinger Bands parameters: time length window(20,144,288), standard deviation(*1, *2)
Period: long period(2010-01-01 to 2024-01-01), short period(2023-01-01 to 2024-01-01)
Timeframe: 1Min, 1H, 1D


## Automation and Scheduling:

The system automates the retrieval of market data and execution of trades using a while loop that runs indefinitely, with a sleep interval to limit the frequency of API calls and adhere to rate limits. This approach ensures that the system remains responsive to market conditions and can execute trades at optimal times.


## Paper Trading and Monitoring:

Utilizing Alpaca's paper trading feature, the system simulates trading activity in a risk-free environment. This allows for the monitoring of the algorithm's performance under live market conditions without financial exposure. Trades, positions, and P&L are logged and reviewed to assess the strategy's effectiveness.


## Results and Lessons Learned:

The backtesting result for strategy implementation from 2023-01-01 to 2024-01-01 is quite good, landing in 5% annual return.

The initiative brought to light the significance of extensive backtesting as well as the ongoing oversight and modification of algorithmic trading techniques. Handling API rate constraints and making sure that data was processed and retrieved accurately were challenges.

## Compliance and Legal Considerations:

The development and operation of the trading system were conducted in compliance with relevant financial regulations and Alpaca's terms of service. Care was taken to ensure data privacy and secure handling of API keys.

Another thing needed to be considered is the transaction cost, which can affect the position change frequency and final expected return.

## Conclusion:

The development and testing of a technical indicator-based trading strategy using Alpaca's paper trading environment was shown to be feasible through this algorithmic trading project. This project has given me a lot of experience and taught me valuable insights that will help me develop and improve automated trading techniques going forward.



