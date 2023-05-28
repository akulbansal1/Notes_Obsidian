
Published: 2 April, 2018
Tags: #Trend_Following 
[Link](https://blog.thinknewfound.com/2018/04/diversifying-the-what-how-and-when-of-trend-following/)

- "an evaluation of the 'long run' can often overshadow many of the short-term risks that can materialise when a model is overly simplistic"
	- "Most strategies look good when plotted over a 100-year period in log-scale"
- "we can tackle several of the uncompensated risks found in naïve implementations [of trend following] by using the three axes of diversification: what, how, and when"


## The What: Asset Diversification
- "when there are more opportunities for diversification, the accuracy hurdle rate that a tactical process has to overcomes increases"
- "a naïvely implemented trend following on U.S. equities over the last century has been exceptionally effective". `The author takes 12-1 months time-series momentum strategy as an example.`
	- This has "worked in a variety of international markets over the long run but the realised performance can be much more volatility than we have with U.S. equities"
- "One approach to providing U.S. equity exposure while diversifying our investments is to use the individual sectors that comprise the index itself"
	- Allocating equally across sector, "we end up with a cumulative excess return graph" very similar to the result in the naïve U.S. equity strategy "but generated with far more internal diversification"
- "We could potentially incorporate other factors (e.g. value or momentum), enforce diversification limits, or even re-invest capital from sectors exhibit negative trend back into those exhibiting positive trends"


## The How: Process Diversification
- Popular methods of implementing trend-following: #idea_trend_following 
	1. Prior total returns ("time-series momentum")
	2. Price-minus-moving-average (e.g. price falls below the 200 day moving average)
	3. Moving-average double cross-over (e.g. the 50 day moving average crosses the 200 day moving average)
	4. Moving-average change-in-direction (e.g. the 200 day moving average slope turns positive or negative)
- Moving-average-double-crossover strategies are "really just an alternative weighting scheme for return in time-series momentum" see [[Trend Filtering Methods for Momentum Strategies|this paper]]
- Time-


## The When: Timing Luck
- [[Quantifying Timing Luck|Related post]]
- Rebalancing luck can be significant over the long run
- "the cure for this problem is simple: diversification. Instead of picking a week to rebalance on, we can allocate to multiple variations of the strategy each rebalancing at a different point in time"
	- "one variation may rebalance on the 1st week of the month, another on the 2nd week, et cetera. This technique is called 'overlapping portfolios' or 'tranche-ing'"