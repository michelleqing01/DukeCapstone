# 📰 News Novelty and Equity Trading - Final Project README

## 🧠 Project Motivation 

Financial markets react rapidly to new information, but not all news has the same impact. This project explores whether the novelty of a news article—how different orsurprising it is compared to past coverage—can be used as a predictive trading signal. 

We hypothesize that high-novelty news events are more likely to trigger significant short-term price reactions, increased trading volume, and potential alpha-generating opportunities. 

## 🔬 Methodology 
We use RavenPack's Novelty Score (0-100 scale) to quantify the informational uniqueness of a news article. We divide novelty into three bins: 
- High Novelty: Top 20th percentile
- Mid Novelty: 45th - 55th percentile
- Low Novelty: Bottom 20th percentile

For each news event, we simulate a trade triggered immediately after the article and test five fixed holding periods:
- 3 minutes
- 10 minues
- 30 minutes
- 60 minutes
- 2 hours
The backtest covers Q1-Q3 of 2022, as later data lacked novelty score coverage.


## 📊 Data and Scope
We analyze equities across different market caps: 
- Large Cap: AAPL, TSLA, NFLX, SPY
- Mid Cap: ARWR, JBLU
- Small Cap: BIG, WSM, UHT, MLNK
  
Trades are simulated using minute to hour-level return data, with equal capital allocation across equities to normalize comparisons and avoid skew from high-priced stocks. 

## 💡 Strategy Summary
Enter after high or low-novelty news. Exit based on holding window & market cap:
- Large Cap -> Low novelty, long hold (60-120 min)
- Mid Cap -> High/mid novelty, long hold (60-120 min)
- Small Cap -> High novelty, long hold (60-120 min)

Allocate fixed capital per trade, avoid short holds for highly volatile stocks. 

## 🎭 Performance
With a simulated $100,000 capital
- Strategy Profit: +$196.64
- Buy-and-Hold Loss; -$11,585.89
- Turnover Rate: 1.0 (capital reinvested after each trade)
- Best performance: large caps with low novelty and long holding window
- Risk: mid/small caps with higher volatility and negative Sharpe Ratios

## 🔮 Future Steps
- Extend testing to Q4 2022-2024 once novelty data is available
- Include more equities, especially from diverse industries
- Test alternative exit signals (ex. price thresholds or volume spikes)
- Incorporate transaction costs & slippage
- Explore cross-asset novelty spillover

  ## 📚 Citations
- RavenPack Documentation (Novelty Score and TAQ Equity Data)
- https://rady.ucsd.edu/why/news/2025/03-18-earnings-news-cause-immediate-stock-price-jumps-sometimes-moving-whole-market.html
- https://www.sciencedirect.com/science/article/abs/pii/S1566014120305872
- https://www.columbia.edu/~pt2238/papers/Tetlock_Media_Sentiment_JF.pdf
- https://finimize.com/content/news-and-markets


---

Duke University | Fuqua School of Business 
Worked with Zhiyig Fan, VP Quant Analytics, Securitized Products—Barclays
