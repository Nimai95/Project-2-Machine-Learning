# **Team 5 - BACKTESTING - Do Moving Average Crossover Trading Strategies Really Work With SPY Over Long Term?**

### Team Members
Hanna Ho, Claudia Martinez, Atousa Mirzaei-Rezaei, Jalal Huseynov

## **Project Description**

Moving Average (MA) Crossover Strategy is very well known and the most simple long-only trading strategy. Signals to buy depend on the crossover of short lookback period over the long lookback period. In contrast, the sell signal is triggered when MA long lookback crosses the MA short lookback. Our goal is to examine whether MA crossover strategies are beneficial for S&P ETF investors from both return and risk perspective. In this project, we will test four popular strategies which are: 50 SMA crossing 200 SMA, 50 SMA crossing 100 SMA, 20 EMA crossing 50 SMA, and 11 EMA crossing the 49 EMA. 

## **The Settings**

* No leverage/margin is used
* Buy and sell is on the close prices when signal is triggered
* All profit/loss will be reinvested in one trade
* No commision/fee/tax is taken into consideration
* Time horizon: 25 years - 1/1/1997 - 12/31/2021


## **Dataset That Was Used**
We used Pandas Datareader to get "SPY" data from yfinance (Yahoo). Even though we did not cover this in the class, we found it easy to use. After we checked the data, we saw that the data was clean and it did not need any cleaning.

---

`from pandas_datareader import data `
 
`import yfinance as yf`

---

`yf.Tickers(tickers)`

`panel_data = yf.download(tickers, start = start_date, end = end_date, interval = interval)`

---

## **Coding Process**

    Our coding process happened in this flow:
    - Import Libraries
    - Declare variables
    - Import "SPY" ETF data
    - Check/Clean data
    - Calculate the benchmark results for our choosen ETF, "SPY"
    - Calculate the results for each strategy: total return, compound annual growth rate ('CAGR'), volatility, Sharpe Ratio, max drawdown ('MDD'), exposure ratio, number of trade, win rate
    - Plot findings
    - Build dashboard for findings

## **Findings**

**Strategy 1 : 50 SMA crossing 200 SMA**


![alt text](images/strategy1_vs_bm_cumulative_return.png "strategy1_vs_bm_cumulative_return")

Above chart shows strategy 1's total return vs SPY total return. In terms of total returns, we can observe that strategy1 started to outperform the benchmark from 2008. The reason was that the sell signal was triggered before the big crash. However, we can see that strategy1 had sold the position late during the 2020 Covid crash which caused it to underperform the benchmark.

![alt text](images/strategy1_drawdown_pct.png "strategy1_drawdown")

This chart shows the strategy1 drawdown period from 1997 to 2021. A drawdown is a peak-to-trough decline during a specific period for an investment. Drawdowns are important for measuring the historical risk of an investment. 

**Strategy 2 : 50 SMA crossing 100 SMA**

![alt text](images/strategy2_vs_bm_cumulative_return.png "strategy2_vs_bm_cumulative_return")

Above chart shows strategy 2's total return vs SPY total return. As we can see from the chart that this strategy never managed to outperform the benchmark. 

![alt text](images/strategy2_drawdown_pct.png "strategy2_drawdown")

This chart shows the strategy2 drawdown period from 1997 to 2021.


**Strategy 3 : 20 EMA crossing 50 SMA**

![alt text](images/strategy3_vs_bm_cumulative_return.png "strategy3_vs_bm_cumulative_return")

Above chart shows strategy 3's total return vs SPY total return. Strategy3 is the worst performing against the bechmark.

![alt text](images/strategy3_drawdown_pct.png "strategy3_drawdown")

This chart shows the strategy3 drawdown period from 1997 to 2021.

**Strategy 4 : 11 EMA crossing the 49 EMA**

![alt text](images/strategy4_vs_bm_cumulative_return.png "strategy4_vs_bm_cumulative_return")

Above chart shows strategy 4's total return vs SPY total return.

![alt text](images/strategy4_drawdown_pct.png "strategy4_drawdown")

This chart shows the strategy4 drawdown period from 1997 to 2021. 

**Comparision of Strategy Returns**

![alt text](images/comparison_cumulative_returns.png "Comparision of strategy returns")

Above chart shows all the strategy returns.

##  **Conclusion**

Several key thoughts we would like to share:
* With just the simple moving average crossover strategy, it's very hard to beat the index with ETF. End of the day, buy and hold strategy seems to be the best, just as same strategy as Benjamin Graham and Warren Buffett )
* Among the four strategies, strategy 1 which is also known as "golden cross" seems to be more effcient than the others in terms of return, volatility, and win rate

## **If We Had More Time...**

If we had more time, the first thing we would do is to perfect the code. This includes writing functions that can be implemented with various strategies. We would also love to calculate new performance indicators and use them to compare the performance of each strategy. In addition, we could test the peformance of other trading indicators including RSI, and MACD.

## **References**

[STOCKBROS RESEARCH](https://www.stockbrosresearch.com/themoneyblog/do-moving-average-crossover-trading-strategies-really-work-backtesting-golden-crosses-and-more )

[LEARNDATASCI](https://www.learndatasci.com/tutorials/python-finance-part-yahoo-finance-api-pandas-matplotlib/)


