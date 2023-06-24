
Published: 20180402
Tags: #Trend_Following 
[Link](https://blog.thinknewfound.com/2018/04/diversifying-the-what-how-and-when-of-trend-following/)

- "an evaluation of the 'long run' can often overshadow many of the short-term risks that can materialise when a model is overly simplistic"
	- "Most strategies look good when plotted over a 100-year period in log-scale"
- "we can tackle several of the uncompensated risks found in naïve implementations [of trend following] by using the three axes of diversification: what, how, and when"


## The What: Asset Diversification
- "when there are more opportunities for diversification, the accuracy hurdle rate that a tactical process has to overcomes increases"
- "a naïvely implemented trend following on U.S. equities over the last century has been exceptionally effective". `The author takes 12-1 months time-series momentum strategy as an example.`![[Screenshot 2023-05-29 at 3.03.20 PM.png]]
	- This has "worked in a variety of international markets over the long run but the realised performance can be much more volatility than we have with U.S. equities"![[Screenshot 2023-05-29 at 3.03.37 PM.png]]
- "One approach to providing U.S. equity exposure while diversifying our investments is to use the individual sectors that comprise the index itself"![[Screenshot 2023-05-29 at 3.04.09 PM.png]]
	- Allocating equally across sector, "we end up with a cumulative excess return graph" very similar to the result in the naïve U.S. equity strategy "but generated with far more internal diversification"![[Screenshot 2023-05-29 at 3.04.31 PM.png]]
- "We could potentially incorporate other factors (e.g. value or momentum), enforce diversification limits, or even re-invest capital from sectors exhibit negative trend back into those exhibiting positive trends"


## The How: Process Diversification
- Popular methods of implementing trend-following: #idea_trend_following 
	1. Prior total returns ("time-series momentum")
	2. Price-minus-moving-average (e.g. price falls below the 200 day moving average)
	3. Moving-average double cross-over (e.g. the 50 day moving average crosses the 200 day moving average)
	4. Moving-average change-in-direction (e.g. the 200 day moving average slope turns positive or negative)
- Moving-average-double-crossover strategies are "really just an alternative weighting scheme for return in time-series momentum" see [[Trend Filtering Methods for Momentum Strategies|this paper]]
- Time-series momentum is related to moving-average-change-in-direction. Time-series momentum signals will not occur until the moving average change direction. [Paper on this](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=2225551)
	- "signals from a price-minus-moving-average strategy are likely to occur before a change in signal from time-series momentum"
- [This paper](obsidian://open?vault=Akul's%20Notebook&file=Library%2Fjournals%2Cmagazines%2FSSRN%20Papers%2FUncovering%20Trend%20Rules.pdf) "explored trend rules with skip periods and the popular MACD rule". "MACD is as much trend following as it is mean-reversion"
- [This paper](obsidian://open?vault=Akul's%20Notebook&file=Library%2Fjournals%2Cmagazines%2FSSRN%20Papers%2FMarket%20Timing%20with%20Moving%20Averages%20Anatomy%20and%20Performance%20of%20Trading%20Rules.pdf) "explored price-minus-moving-average, moving-average-double-crossover, and moving-average-change-of-direction [...] can be interpreted as the computation of a weighted moving average of momentum rules with different look-back periods"
- The plot shows maximum return difference over rolling 5-year periods between four different trend following approaches.![[Screenshot 2023-05-29 at 3.01.56 PM.png]]
	- "the long-term average spread was 348 bps and the median was 306 bps"
	- "no approach was a consistent winner or loser"
	- "model choice represents an uncompensated risk that we bear as a manager. Using multiple methods, then, is likely a prudent course of action"
- Another plot shows the difference between the best and the worst look-back horizon over rolling 5-year periods.![[Screenshot 2023-05-29 at 3.02.10 PM.png]]
	- "5-year annualized returns between parameterizations frequently deviate by more than 500 bps"
	- "optimal parameterization is highly regime dependent"
	- "we end up bearing unnecessary parameterization risk, and diversification is a prudent action"


## The When: Timing Luck
- [[Quantifying Timing Luck|Related post]]
- Rebalancing luck can be significant over the long run
- "the cure for this problem is simple: diversification. Instead of picking a week to rebalance on, we can allocate to multiple variations of the strategy each rebalancing at a different point in time"
	- "one variation may rebalance on the 1st week of the month, another on the 2nd week, et cetera. This technique is called 'overlapping portfolios' or 'tranche-ing'"