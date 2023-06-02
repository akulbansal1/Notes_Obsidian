

Published: 1 Sept, 2020
Tags: #Risk_Management #Forecasting #Rob_Carver 
[Link](https://qoppac.blogspot.com/2020/09/forecast-linearity-and-forecasting-mean.html)

This is part 2 in four part series
[[Do non binary forecasts work?|Part 1]]
[[Should I run my trading system at a fixed expected volatility target?|Part 3]]

- "Our forecasts are on risk adjusted returns, which are joint forecasts of return and volatility. We also use forecasted vol to size positions. A better vol forecast should mean we end up with a trading strategy that has a nice return profile"

- To see the result of forecast strength on the forward realised volatility, Rob plotted "forecast on the x-axis, and the ratio of actual versus expected vol on the y-axis. Effectively then this is a measure of how good we are at forecasting vol, conditional on forecast strength"![[Screenshot 2023-06-01 at 6.22.20 PM.png]]
	- "If we were good at forecasting vol, irrespective of forecast, this would be a flat line intercepting the y-axis at y=1"
	- "When forecasts are large, actual vol turns out to be relatively high compared to expected vol. When forecasts are small, actual vol is a little lower than expected"

- Explanations for the realised risk-adjusted returns flatting out at extreme forecasts:
	1. Vol is mean reverting, regardless of risk-adjusted return forecast value; or
	2. We get uniquely bad at forecasting vol when forecasts are really big
- "doing a better job of vol forecast seems like a noble goal in itself"

- A really simple thing we can do is replace our vol forecast with:![[Screenshot 2023-06-01 at 6.21.49 PM.png]]
	vol_slow is the 10 year average for volatility

- Using moving averages of different lookback lengths to calculate the average volatility observed in the past:
	1. Current (roughly vol from the last 30 days)
	2. 3 month MA
	3. 6 month MA
	4. 12 month MA
	5. 2 year MA
	6. 5 year MA
	7. 10 year MA
- Setup the regression with the future vol as y variable, and the following as the x variables:
	1. Current
	2. 6m MA - 3m MA
	3. 1y MA - 6m MA
	4. 2y MA - 12m MA
	5. 5y MA - 2y MA
	6. 10y MA - 5y MA
	7. 10y MA - current vol
- Regressing these variable with future realised volatility will give the value of 'p' for the lookback.

Summary
- "problem: forecasts reverting in the wings"
	- Explanation: high risk adjusted return forecast values were associated with vol forecasts that were systematically too low; explanation for this seemed to be mean reverting vol
- "I did manage to remove most of the bias in vol forecasts conditioned on risk adjusted return forecasts, but the reversion in the wings of risk adjusted return forecasts did not go away"