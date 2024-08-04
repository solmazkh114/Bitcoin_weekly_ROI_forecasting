This project is about forecasting the weekly Return on Investment (ROI) of Bitcoin. I was attracted to work on this project since it was one of the [Trilemma Capital Tournaments](https://www.trilemmacapital.com/tournament).
The main question they were seeking to answer was:

Given the Bitcoin price at 1 PM Pacific Time (20:00 PM GMT) on each Monday, what will the ROI be at 1 PM Pacific Time (20:00 PM GMT) on the next Monday?

Their reference rate for the spot price of Bitcoin was the CoinDesk Bitcoin Price Index (CDIXBX). Since I could not find an API or Python library to provide such data, 
I used the Crypto Coin Comparison Aggregated Index (CCCAGG) provided by the CryptoCompare platform. I had three reasons to use this index:

- I could easily get Bitcoin price data using the `cryptocompare` Python library.
- The methodology used for computing this index is based on a 24-hour volume-weighted average calculation, a time-penalty factor, and outlier methodology (for more information see [CCCAGG Index Methodology](chrome-extension://efaidnbmnnnibpcajpcglclefindmkaj/https://www.cryptocompare.com/media/37746014/cccagg_index_methodology_2021_02.pdf)). This makes it a good estimation of BTC across various indices.
- In this project, we did not explicitly need the exact Bitcoin rate. Actually, we were interested in the weekly ROI metric, which is based on the difference between two BTC prices. Thus, it does not really matter which indices we use.

In this project, we tried various methods including statistical models, deep learning models and gradient-boosting methods to forecast this metric. 
The final model performance is promising, as it outperformed the baseline model with a benchmark MAE < 3.
