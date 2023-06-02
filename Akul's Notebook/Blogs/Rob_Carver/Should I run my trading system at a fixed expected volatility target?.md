

Published: 
Tags: #Risk_Management #Portfolio_Management #Rob_Carver 
[Link](https://qoppac.blogspot.com/2020/10/should-i-run-my-trading-system-at-fixed.html)

This is part 3 in four part series
[[Do non binary forecasts work?|Part 1]]
[[Forecasting linearity and forecasting mean reverting volatility|Part 2]]

- Actual volatility of the portfolio might be quite different from the volatility that is being targeted due to:
	1. Forecasting. Higher forecast = higher risk in the position
	2. Correlation. Diversification multiplier has been calculated based on historical correlation, which could vary drastically over the short term
- "the main disadvantage of this approach [target volatility at the portfolio level] is that you lose any information provided by the forecasts. In a period when forecasts are generally low, we'd gear up our positions to hit the target risk, and the converse would be true when forecasts were high"
- Expected risk = target risk * (relative forecast strength) * (relative correlation factor)
	- Read [[Exogenous risk management]]
	- "Relative forecast strength is a measure of how strong aggregate forecasts are relative to the average"
	- "relative correlation factor (RCF) […] is equal to the ratio between the IDM (which accounts for the average correlation across subsystem returns), and the IDM that would be appropriate today given the current set of positions and current correlation between instrument returns"
	- "the RCF can vary quite a lot depending on what the current positions are, and the current correlation matrix

- [[Do non binary forecasts work?]] shows "that forecast strength was indeed an indicator of future performance", to check if having binary forecasts made more sense.
	- If aggregate forecasts have any predictive power, then it will not make sense to target risk on the portfolio level, i.e. lowering exposure on the portfolio level based on recent realised volatility
- Targeting a fixed risk on portfolio level worsens performance (a drop in Sharpe Ratio from 0.93 to 0.64)
	- Look at the back-test; Orange line: Account curve without fixed risk targeting; Blue curve: Account curve with fixed risk targeting
- Adjusting risk based only on changes in correlations and positions is slightly better than just adjusting risk on the portfolio level, but the performance overall still lags the original method of not adjusting risk on the portfolio level

Conclusion

- "The simpler fixed risk target idea, where we target 25% annualised risk or whatever every single day, is a non-starter […] and the reason why is clear - it throws away the information provided by aggregate forecast strength, which is a clear predictor of future risk adjusted return"